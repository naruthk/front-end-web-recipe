# Data Structures

An overview of common data structures to know for technical interviews.

Huge credit to the **Cracking the Coding Interview** book for all the fabulous content.

## Table of Content

<!-- TOC -->

- [Data Structures](#data-structures)
  - [Table of Content](#table-of-content)
  - [Hash Tables](#hash-tables)
  - [ArrayList](#arraylist)
  - [StringBuilder](#stringbuilder)

<!-- /TOC -->

## Hash Tables

A data structure that maps keys to values and offers efficient lookup.

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

## ArrayList

In Java, an **array** has a fixed size because its size is defined when created. To achieve **dynamic resizing**, use an **ArrayList**.

**Runtime:**

- Inserting a value:
  - Amortized: `O(1)`
  - Worse case: `O(N)` because an array is full

## StringBuilder

A **StringBuilder** creates a resizable array of all the strings and copies them back to a string only when necessary.

If we don't rely on using a StringBuilder, then the concatenation of strings will take `O(N^2)` time, which is slow.