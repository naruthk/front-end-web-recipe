# Data Structures

What you'll find here are some general data structures that are worth knowing about.

<!-- TOC -->

- [Data Structures](#data-structures)
    - [StringBuilder](#stringbuilder)
    - [HashMap](#hashmap)

<!-- /TOC -->

## StringBuilder

A **StringBuilder** creates a resizable array of all the strings and copies them back to a string only when necessary.

If we don't rely on using a StringBuilder, then the concatenation of strings will take `O(N^2)` time, which is slow.

## HashMap

A *hash table* based implementation of the **Map interface**.

```java
// Declaration:
Map<String, String> myMap = new HashMap<String, String>();
```

**Useful methods:**

- `containsKey(Object key)` - Returns true if the key exists. Return false is not found.
- `get(Object key)` - Returns the value of that key
- `put(K key, V value)` - Adds the (key, value) mapping to the Map. Overwrites any existing value.