# C Language Cheatsheet

## Basics

### Variables and Types
```c
int a = 10;                 // Integer
double pi = 3.14;           // Floating-point number
char c = 'A';               // Character

// Array declaration
int array[5] = {1, 2, 3, 4, 5};
```

### Constants
```c
#define PI 3.14159
const int max = 100;
```

### Printing Output
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    printf("PI = %.2f\n", PI);
    return 0;
}
```

### Functions
```c
int add(int x, int y) {
    return x + y;
}

// Function prototype
int multiply(int x, int y);
```

## Control Structures

### If Statement
```c
if (a > 0) {
    printf("a is positive\n");
} else if (a < 0) {
    printf("a is negative\n");
} else {
    printf("a is zero\n");
}
```

### Loops
```c
// For loop
for (int i = 0; i < 5; i++) {
    printf("%d\n", i);
}

// While loop
int i = 0;
while (i < 5) {
    printf("%d\n", i);
    i++;
}

// Do-while loop
int j = 0;
do {
    printf("%d\n", j);
    j++;
} while (j < 5);
```

### Switch Statement
```c
switch (a) {
    case 1:
        printf("One\n");
        break;
    case 2:
        printf("Two\n");
        break;
    default:
        printf("Other\n");
}
```

## Data Structures

### Structs
```c
struct Point {
    int x;
    int y;
};

struct Point p1 = {1, 2};
```

### Pointers
```c
int var = 10;
int *ptr = &var;    // Pointer to var

printf("Value: %d\n", *ptr);  // Dereferencing pointer
```

### Dynamic Memory Allocation
```c
#include <stdlib.h>

int *arr = malloc(10 * sizeof(int));  // Allocate array dynamically
if (arr != NULL) {
    for (int i = 0; i < 10; i++) {
        arr[i] = i;
    }
}

free(arr);  // Free allocated memory
```

## Libraries

### Standard I/O Library
```c
#include <stdio.h>

// File operations
FILE *fp = fopen("file.txt", "r");
if (fp == NULL) {
    perror("Error opening file");
} else {
    fclose(fp);
}
```

### Standard Library
```c
#include <stdlib.h>
#include <string.h>

// Conversion
int val = atoi("123");

// Memory operations
char str1[10];
strcpy(str1, "hello");     // Copy string
```

## Preprocessor Directives
```c
#include <stdio.h>   // Include standard input/output header

#define MAX 100      // Define constant
#if MAX > 99
#error "MAX is too large"
#endif
```

## Debugging
```c
#include <assert.h>

int main() {
    int x = 7;
    assert(x == 7);  // Assert x is 7
    return 0;
}
```
