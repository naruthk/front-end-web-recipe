# Multidimensional Arrays

**To create a **2 x 4** matrix:**

```java
int rowSize = 2;
int colSize = 4;
int[][] myArray = new int[rowSize][colSize];
```

Here's how it is represented graphically:

```java
// (0, 0) (0, 1) (0, 2) (0, 3)
// (1, 0) (1, 1) (1, 2) (1, 3)
```

**Accessing a multidimensional array:**

```java
for (int i = 0; i < rowSize; i++) {
  for (int j = 0; j < colSize; i++) {
    System.out.print(myArray[i][j] + " ");
  }
}
```

```java
// 0 1 2 3
// 4 5 6 7
```

Notice that the outer loop represents the row, while the inner loop represents the column.