# Day 4 – Functions, Variables, and Code Blocks in Rust 🦀

## 📌 What I Learned
- `fn` defines a function.
- `main()` is the entry point of Rust programs.
- `{}` creates a code block.
- `println!` is a macro used to print values.
- Functions can return values using `->`.
- Variables can be defined inside code blocks (scope rules).
- Created a `multiply` function.

---

## 📝 Example Code

```rust
fn main() {
    println!("Hello, world!");

    // fn means function
    // main means start the function
    // () → function parameters (empty here)
    // { } → code block
    // println! → macro (special function)

    println!("Hello world number {} and {}", 8, 9);
    println!("number is {}", number()); // Calling a function

    multiply(8, 9);

    // Multiply using variables
    let some_number = 4;
    let some_other_number = 2;
    multiply(some_number, some_other_number);

    // Declaring variable inside a block
    let my_number2 = {
        let second_number = 8;
        second_number + 9
    };

    println!("new number is {}", my_number2);
}

// Creating a number function
fn number() -> i32 {
    8
}

// Multiply function
fn multiply(number_one: i32, number_two: i32) {
    let result = number_one * number_two;
    println!("{} x {} is {}", number_one, number_two, result);
}
