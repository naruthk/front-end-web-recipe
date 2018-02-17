<!-- TOC -->

- [Is Unique: Implement an algorithm to determine if a string has all unique characters. What if you cannot use additional data structures?](#is-unique-implement-an-algorithm-to-determine-if-a-string-has-all-unique-characters-what-if-you-cannot-use-additional-data-structures)
- [Check Permutation: Given two strings, write a method to decide if one is a permutation of the other.](#check-permutation-given-two-strings-write-a-method-to-decide-if-one-is-a-permutation-of-the-other)

<!-- /TOC -->

## Is Unique: Implement an algorithm to determine if a string has all unique characters. What if you cannot use additional data structures?

```java
// Runtime: O(N). Go through each character in the string once.
public boolean isUnique(String str) {
  boolean[] array = new boolean[str.length()];
  for (int i = 0; i < str.length(); i++) {
    int index = str.charAt(i) - '0';
    if (array[index]) {
      return true;
    }
    array[index] = true;
  }
  return false;
}
```

## Check Permutation: Given two strings, write a method to decide if one is a permutation of the other.

```java
// Runtime: O(N) by going through every character in the string
public boolean isPermutation(String s1, String s2) {
  if (s1.length()  != s2.length()) {
    return false;
  }
  char[] sorted1 = s1.toCharArray().sorted();
  char[] sorted2 = s2.toCharArray().sorted();
  for (int i = 0; i < sorted1.length(); i++) {
    if (!sorted1[i].equals(sorted2[i])) {
      return false;
    }
  }
  return true;
}
```