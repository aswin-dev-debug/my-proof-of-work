# 🦀 Rust Learning Journey — Day 16: Control Flow

Today’s topic: **Control Flow in Rust**

I explored how to control program logic using `if`, `else if`, `else`, and the powerful `match` statement with **pattern matching** and **match guards**.

---

## 🧠 Concepts Covered

- Using `if`, `else if`, and `else` conditions  
- Logical operators: `&&` (AND) and `||` (OR)  
- The `match` expression as a cleaner alternative to multiple `if` statements  
- Matching tuples and combining conditions  
- Match guards: adding conditional checks inside `match` arms  

---

## 🧩 Code Example

```rust
// Control Flow in Rust

fn main() {
    // Simple if condition
    let my_number = 7;
    if my_number == 7 {
        println!("It's seven");
    }

    // If-else condition
    let my_number = 5;
    if my_number == 7 {
        println!("It's seven");
    } else if my_number == 6 {
        println!("It's six");
    } else {
        println!("It's a different number");
    }

    // Using logical operators (&& for AND, || for OR)
    let my_number = 5;
    if my_number % 2 == 1 && my_number > 0 {
        println!("It's a positive odd number");
    } else if my_number == 6 {
        println!("It's six");
    } else {
        println!("It's a different number");
    }

    // Using match — a cleaner alternative to nested if/else
    let my_number: u8 = 5;
    match my_number {
        0 => println!("It's zero"),
        1 => println!("It's one"),
        2 => println!("It's two"),
        _ => println!("Different number"),
    }

    // Matching tuples
    let sky = "clear";
    let temperature = "warm";

    match (sky, temperature) {
        ("cloudy", "cold") => println!("It's dark and unpleasant today"),
        ("clear", "warm") => println!("It's a nice day"),
        ("cloudy", "warm") => println!("It's dark but not bad"),
        _ => println!("Not sure what the weather is."),
    }

    // Match guard example
    let children = 5;
    let married = true;

    match (children, married) {
        (children, married) if married == false => println!("Not married with {} children", children),
        (children, married) if children == 0 && married == true => println!("New married couple, no children"),
        _ => println!("Married? {}. Number of children: {}.", married, children),
    }
}
