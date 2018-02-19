# Hash Tables

A data structure that maps keys to values and offers efficient lookup. A **hash table** data structure is just an array where the data is stored into this array at specific indices computed by a **hash function**.

**Requirements:**

- An array of type **Linked Lists**
- A **Hash Code Function** to compute the key's hash code and map it to an index in the array

**Steps:**

1. Find out the key's hash code (usually `int` or `long`). Multiple keys can have the same hash code (*collision*).
2. Using the hash code, map it to an index in the array. `array[index]` where `index` is `hashCode(key) % array.length`.
3. Store the key and value (inserting it to the end of the Linked List at this particular index of the array).

**Runtime:**

- Looking up a value:
  - Best case: `O(1)`
  - Worse case: `O(N)` because there are multiple elements in the Linked List

## HashCode Function

A **hash function** is a mapping between a set of values and a set of integers (**hash values**).

Take a look at this example, where `101` is the hash value. (Note this is *not* a good hash function)

```java
public int hash(char c, int tableSize) {
    return 101 % tableSize;
}
```

The example above demonstrates how a hash function works. The function returns a value that is determined by getting the remainder of `101` divided by the size of the table.

Arguably, `101` isn't the best number to used because what we want to aim for is a **good uniform distribution** for our set of data. We don't want most of our data in the set to be placed in only a few indices of our array. We want them to spread out as evenly as possible. Therefore, the hash function above isn't the best.

The Internet is filled with lots of awesome hash functions you should take a closer look at. [Here's a good one from StackOverFlow.](https://stackoverflow.com/questions/113511/best-implementation-for-hashcode-method)

## Avoiding Collision

Two data may hash to the same integer value that determines the index in the array. We call this scenario as a **collision**.

Many novice consider expanding the size of the hash table (implemented with an array), hoping for a lower rate of collision. But that's not helpful because they're basically **wasting memory space**.

## Solving Collision

Three common solutions exist:

- Linear Probing
- Quadratic Probing
- Separate Chaining

### Linear Probing

Say the element has been hashed to a particular location in the array. It turns out that that another element already occupies that index. So from that index onward, we look for the next unoccupied index to place our element inside.

Represented in terms of Math expressions, linear probing begins by trying to place the element at index `n`. When fails, it increments to `n + 1`, `n + 2`, `n + 3`, and so on.

Generic form: `(n + i) % tableSize`, where `i` is incremental.

### Quadratic Probing

This is similar to linear probing, except that **quadratic probing** begins at `n`, and then `n + 1`, `n + 4`, `n + 9`, and so on until it finally sees an available spot.

Generic form: `(n + i^2) % tableSize`, where `i` is incremental.

A special (and bad) thing that can happen with quadratic probing is that if your hash table is almost *half full*, there's a chance that quadratic probing will no longer work at all because mathematically there is no guarantee that you will ever find the next available spot.

### Separate Chaining

With this method, our array is made up of Linked Lists. Each time an element hashes to a location that is already occupied, it doesn't look anywhere else. The element is appended to the end of the Linked List for that particular index.

But even separate chaining alone does not represent the world's most beautiful solution. In the worst scenario possible, your hash function sucks and all the elements then hash to the same index. The search operation for this particular scenario is O(N), rather than the normal O(1).