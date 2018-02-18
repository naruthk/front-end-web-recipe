# Binary

<!-- TOC -->

- [Binary](#binary)
  - [How Are Numbers Computed in Binary?](#how-are-numbers-computed-in-binary)
  - [Converting a Number from Base 2 to Base 10](#converting-a-number-from-base-2-to-base-10)
  - [Converting a Number from Base 10 to Base 2](#converting-a-number-from-base-10-to-base-2)
  - [Operations](#operations)
    - [Addition](#addition)
  - [What About Negative Numbers?](#what-about-negative-numbers)
    - [Two's Complement](#twos-complement)
    - [Extending the Sign](#extending-the-sign)

<!-- /TOC -->

How to approach the concept of binary? Think of it as a light switch. There's not much you can do with a light switch. It's either "On" or "Off". When you turn the light switch on, this represents a value of `1` in binary. When the switch is off, this represents a value of `0` in a binary number system.

In computer science, `True` has a value of `1`, while `False` has a value of `0`.

## How Are Numbers Computed in Binary?

**It's easier to first consider Base 10**. A base 10 generally means `A * 10^0 + B * 10^1 + C * 10^2...`. And `A, B, C, ...` each represents any digits from 0 - 9.

For example, the number **`723`** in Base 10 is just `7 * 10^2 + 2 * 10^1 + 3 * 10^0`.

So in general, the expression for Base 10 is `A * B^D` where `A` is the number, `B` is the base, and `D` is the digit location.

**But in binary, everything is Base 2**! 

This means `A * 2^0 + B * 2^1 + C * 2^2...`.

For example, the number **`7`** is represented as `111` in binary. Here's how to break it down:

- Read `111` from right-to-left
- From the right, `1` means `1 x 2^0` which is 1.
- Second from the right, `1` means `1 * 2^1`, which is 2
- From the left, `1` means `1 * 2^2`, which is 4.
- Add `1 + 2 + 4` and we get `7`!

## Converting a Number from Base 2 to Base 10

Remember to read from right to left.

**1110**:

- `0` means `0 * 2^0`, which is 0
- `1` means `1 * 2^1`, which is 2
- `1` means `1 * 2^2`, which is 4
- `1` means `1 * 2^3`, which is 8

So `1110` is `8 + 4 + 2 + 0`, or `14`!

## Converting a Number from Base 10 to Base 2

The approach is to divide the amount by 2, keep track of the remainder, and repeat the two processes again with the result of the division.

Doesn't make sense? Let's use an example.

**34**:

- Divide `34` by `2`.
  - Answer =  `17` (use this for the next division)
  - Remainder = `0` (keep this)
- Divide `17` by `2`.
  - Answer =  `8`
  - Remainder = `1`
- Divide `8` by `2`.
  - Answer =  `4`
  - Remainder = `0`
- Divide `4` by `2`.
  - Answer =  `2`
  - Remainder = `0`
- Divide `2` by `2`.
  - Answer =  `1`
  - Remainder = `0`
- Divide `1` by `2`.
  - Answer =  `0`
  - Remainder = `1`

What we'll use are the remainders that we have been keeping track of.

`34` in Base 2 (binary) is `100010`. 

Notice that first digit on the left our binary is the last remainder we have got from dividing `1` by `2`.

## Operations

`0 + 0` = `0`
`1 + 0` = `1`
`1 + 1` = `0` (not `2` because in binary `2` does not exist)

### Addition

**7 + 7**

We know it's 14. But what if we are given this instead: `111 + 111`? Let's try adding them.

```
  1 1 1
+ 1 1 1
-------
1 1 1 0
```

`1110` is `(0 * 2^0) + (1 * 2^1) + (1 * 2^2) + (1 * 2^3)`, or `0 + 2 + 4 + 8`, which is 14.

## What About Negative Numbers?

Say you have the number `12`, which in binary, is represented as `00001100`.

There are two ways to "flip" the number, making it negative:

- Two's Complement
- "Extending the Sign"

### Two's Complement

Memorize this: 1) Flip the bits, and 2) Add 1

**Let's say we want to turn the number 12 into -12.**

If `12` in binary is `00001100`, we first flip the bits.

```
// Original:  0 0 0 0 1 1 0 0
// Flipped:   1 1 1 1 0 0 1 1
```

We then add 1 to the flipped version.

```
// Flipped:   1 1 1 1 0 0 1 1
            +               1
            -----------------
              1 1 1 1 0 1 0 0
```

That's `-12`.

What's interesting is we can also turn `-12` back to `12` by flipping the bits and adding 1. How cool!

### Extending the Sign

Remember that a byte is 8 bits? That means something along the lines of `10111101` (just anything with 8 binary numbers).

But, say, the number `6` is represented as only `110` in binary. That's only 3 bits. **How do we turn from 6 bits into 8 bits?**

We simply add more zeros in front until it becomes an 8 bit. The answer will remain the same!

`6` = `110` (3 bits) or `00000110` (8 bits).