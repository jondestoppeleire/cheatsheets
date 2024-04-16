# Rust Language Cheatsheet

## Basics

### Variables and Mutability
```rust
let x = 5;                 // Immutable by default
let mut y = 5;             // Mutable variable
```

### Constants
```rust
const MAX_POINTS: u32 = 100_000;
```

### Data Types
```rust
// Integer types
let x: i32 = -5;           // Signed 32-bit integer
let y: u32 = 5;            // Unsigned 32-bit integer

// Floating-point types
let f: f64 = 3.14;         // Double precision floating-point number
let g: f32 = 3.14;         // Single precision floating-point number

// Boolean type
let t: bool = true;

// Character type
let c: char = 'z';
```

### Printing
```rust
println!("Hello, world!");                   // Basic printing
println!("{} days", 31);                     // Positional arguments
println!("{0}, this is {1}. {1}, this is {0}", "Alice", "Bob");  // Named arguments
println!("{name} likes {activity}", name="John", activity="coding");  // Placeholder names
```

### Functions
```rust
fn add(x: i32, y: i32) -> i32 {
    x + y
}
```

## Control Structures

### If Statement
```rust
if x > 5 {
    println!("x is greater than 5");
} else if x < 5 {
    println!("x is less than 5");
} else {
    println!("x is 5");
}
```

### Loops
```rust
// Infinite loop
loop {
    println!("again!");
    break;
}

// While loop
while x < 5 {
    println!("{}", x);
    x += 1;
}

// For loop
for number in 1..4 {
    println!("{}", number);
}
```

## Data Structures

### Tuples
```rust
let tup: (i32, f64, u8) = (500, 6.4, 1);
let (x, y, z) = tup;       // Destructuring
println!("The value of y is: {}", y);
```

### Arrays
```rust
let a = [1, 2, 3, 4, 5];   // Fixed size
let first = a[0];          // Accessing elements
```

### Vectors
```rust
let mut v = Vec::new();    // Mutable vector
v.push(5);                 // Adding an element
```

### Structs
```rust
struct User {
    username: String,
    email: String,
    sign_in_count: u64,
    active: bool,
}

let user1 = User {
    email: String::from("someone@example.com"),
    username: String::from("someusername123"),
    active: true,
    sign_in_count: 1,
};
```

### Enums
```rust
enum IpAddrKind {
    V4,
    V6,
}

let four = IpAddrKind::V4;
let six = IpAddrKind::V6;
```

## Error Handling

### Using `Result`
```rust
fn check_number(num: i32) -> Result<i32, String> {
    if num < 5 {
        Ok(num)
    } else {
        Err(String::from("number is too high"))
    }
}
```

### Using `panic!`
```rust
if x < 5 {
    panic!("x cannot be less than 5!");
}
```

## Ownership and Borrowing

### Ownership
```rust
let s1 = String::from("Hello");
let s2 = s1;  // s1 is no longer valid here
```

### Borrowing
```rust
let s1 = String::from("Hello");
let s2 = &s1;  // s1 is borrowed by s2
println!("{}", s1);  // Still accessible
```

## Concurrency

### Threads
```rust
use std::thread;

let handle = thread::spawn(|| {
    for _ in 1..10 {
        println!("hi number {} from the spawned thread!", i);
    }
});

handle.join().unwrap();
```

## Macros

### `println!`
```rust
println!("Hello, world!");
```

