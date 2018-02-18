# Concurrency

A property of programs and systems that allow for tasks to run in overlapping period of time.

## Parallelism

Although **parallelism** makes it possible for the computer to do multiple things at once, it also introduces lots of problems.

The common problems are **Race Condition** and **Dead Lock**.

### Race Condition

Imagine if two banking transactions occur at roughly the same time. This result in either you losing/gaining more money than intended. That's bad.

Or, in another scenario, imagine if you're trying to update the value of a number, while another person is also trying to do exactly the same thing as well. Who's going to get the accepted value? How are we going to deal with this type of situation?

There are two fundamental ways to solve the problem of race condition:

- Mutual Exclusion (Mutex)
- Semaphore (Binary and Counting)

More on these solutions later.

### Dead Lock

This problem arises when two separate processes come clashing into each other. Each process wants access of the other, but it is individually locked because a prior process has not yet been completed yet.

Think of it this way:

- I want to give my friend, Tony, $10 dollars.
- I made the transfer, and so now my account is locked until the transaction is completed. My bank reaches out to Tony's to finalize the transfer.
- Tony, meanwhile, decides to pay me $5 as well.
- Now Tony's account is locked, waiting for access to my account to complete the transaction.
- We now want access to each other's account in order to complete the transactions.
- We're both stuck. We can't do anything.

## What Are Some Solutions Out There?

### Mutual Exclusion (Mutex)

The system locks the process A from running, which allows process B to finish its task first.

But what if we want a better way to solve this problem?

### Semaphore

There's two types:

- **Binary Semaphore**
- **Counting Semaphore**.

#### Binary Semaphore

The one with higher priority will gain access first. Presumably, `1` means high priority and `0` means low.

#### Counting Semaphore

It allows more than 1 process to run at the same time.

I like this answer from [Carl Cheo's site](http://carlcheo.com/compsci). He said, "Let’s say you’re a locker room manager for a spa. There are 30 lockers. You have to keep track of the number of keys you have each time you receive or hand out a key, but you don’t exactly know who they are. **If all lockers are full, others have to queue up.** Whenever someone is done, **he/she will hand over the key to the first person** in the queue.".