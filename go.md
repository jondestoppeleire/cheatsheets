# Go Language Cheatsheet

## Basics

### Variables
```go
var a int = 10            // explicit type
var b = 10                // type inferred
c := 10                   // shorthand, type inferred
```

### Constants
```go
const Pi = 3.14
const (
    StatusOK = 200
    NotFound = 404
)
```

### Basic Types
```go
bool        // Boolean type
int, int8, int16, int32, int64      // Integers
uint, uint8, uint16, uint32, uint64 // Unsigned integers
float32, float64   // Floating point numbers
complex64, complex128 // Complex numbers
string      // String type
```

### Functions
```go
func add(x int, y int) int {
    return x + y
}

// multiple return values
func swap(x, y string) (string, string) {
    return y, x
}
```

## Control Structures

### If Statement
```go
if x > 0 {
    fmt.Println("x is positive")
} else if x < 0 {
    fmt.Println("x is negative")
} else {
    fmt.Println("x is zero")
}
```

### Loops
```go
// For loop
for i := 0; i < 10; i++ {
    fmt.Println(i)
}

// While loop
j := 0
for j < 10 {
    fmt.Println(j)
    j++
}

// Infinite loop
for {
    // logic here
}
```

### Switch Statement
```go
switch os := runtime.GOOS; os {
case "darwin":
    fmt.Println("OS X.")
case "linux":
    fmt.Println("Linux.")
default:
    // freebsd, openbsd,
    // plan9, windows...
    fmt.Printf("%s.\n", os)
}
```

## Data Structures

### Arrays
```go
var a [5]int
a[0] = 1
b := [5]int{1, 2, 3, 4, 5}
```

### Slices
```go
s := []int{1, 2, 3}
s = append(s, 4)
```

### Maps
```go
m := make(map[string]int)
m["a"] = 1
```

### Structs
```go
type Vertex struct {
    X, Y int
}

v := Vertex{1, 2}
v.X = 4
```

## Concurrency

### Goroutines
```go
go func() {
    fmt.Println("Hello from goroutine")
}()
```

### Channels
```go
ch := make(chan int)
go func() {
    ch <- 123  // sending data to channel
}()
v := <-ch    // receiving data from channel
```

### Select
```go
select {
case ch1 <- v:
    fmt.Println("sent v to ch1")
case x := <-ch2:
    fmt.Println("received", x, "from ch2")
default:
    fmt.Println("no communication")
}
```

## Error Handling
```go
if err != nil {
    log.Fatal(err)
}
```

## Packages and Importing
```go
import "fmt"
import (
    "os"
    "time"
)
```

## Comments
```go
// single line comment

/*
Multi-line
comment
*/
```
