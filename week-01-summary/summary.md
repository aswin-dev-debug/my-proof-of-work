# 📅 Weekly Reflections – Week 1 (Rust Learning: Day 1–7)

This document contains a test session to revise all concepts from **Day 1–7** of my Rust learning journey.
The structure includes **MCQs, Fill in the blanks, Debugging, Short Answers**.
At the end, an **Answer Key + Explanations** is provided.

---

## ✅ Concepts Covered (Day 1–7)

1. Rust basics – variables, mutability (`let`, `mut`).
2. Data types: integers, floats, booleans, characters.
3. Shadowing.
4. Constants (`const`) vs immutability.
5. Functions (parameters, return values).
6. Control flow: `if`, `else`, `loop`, `while`, `for`.
7. Strings: `String` vs `&str`.

---

## 📌 Section 1: Multiple Choice Questions (MCQs)

**Q1.** What keyword is used in Rust to declare a mutable variable?
a) `let`
b) `mut`
c) `let mut`
d) `var`

---

**Q2.** Which of the following is **heap allocated** in Rust?
a) `&str`
b) `String`
c) `i32`
d) `bool`

---

**Q3.** What is the correct way to define a constant in Rust?
a) `let PI = 3.14;`
b) `mut const PI:f32 = 3.14;`
c) `const PI:f32 = 3.14;`
d) `PI = 3.14;`

---

**Q4.** Which loop is best suited for iterating over a range in Rust?
a) `loop`
b) `while`
c) `for`
d) `repeat`

---

**Q5.** In Rust, shadowing allows:
a) Mutating immutable variables directly
b) Re-declaring a variable with the same name
c) Allocating memory on heap
d) None of the above

---

## 📌 Section 2: Fill in the blanks

**Q1.** In Rust, the keyword `_____` is used to define a constant value.

**Q2.** The type `String` is stored on the `_____`, while `&str` is a `_____`.

**Q3.** A function in Rust is declared using the keyword `_____`.

**Q4.** Rust ensures memory safety through its `_____` and `_____` system.

**Q5.** The loop that runs forever unless manually broken is called `_____`.

---

## 📌 Section 3: Debugging

**Q1.** Find the error in the following code and correct it:

```rust
fn main() {
    let number = 10;
    number = number + 5;
    println!("{}", number);
}
```

---

**Q2.** Fix the function so that it correctly returns a string:

```rust
fn greet() -> &str {
    let msg = String::from("Hello Rust!");
    &msg
}
```

---

**Q3.** Identify the mistake in this loop:

```rust
fn main() {
    let nums = [1, 2, 3];
    for i in 0..=nums.len() {
        println!("{}", nums[i]);
    }
}
```

---

## 📌 Section 4: Short Answer Questions

**Q1.** Explain the difference between `let` mutability and `const`.

**Q2.** What is shadowing in Rust? Provide an example.

**Q3.** Explain ownership briefly and why Rust enforces it.

**Q4.** Why are strings in Rust UTF-8 by default?

**Q5.** Write a small function in Rust that takes an integer and returns whether it is even or odd.

---

# 📝 Answer Key + Explanations

### ✅ Section 1: MCQs

* Q1 → **c) let mut**
* Q2 → **b) String**
* Q3 → **c) const PI:f32 = 3.14;**
* Q4 → **c) for**
* Q5 → **b) Re-declaring a variable with the same name**

---

### ✅ Section 2: Fill in the blanks

1. `const`
2. Heap, string slice
3. `fn`
4. Ownership, borrowing
5. `loop`

---

### ✅ Section 3: Debugging

**Q1 Fix:**

```rust
fn main() {
    let mut number = 10; // add mut
    number = number + 5;
    println!("{}", number);
}
```

**Q2 Fix:**

```rust
fn greet() -> String {  // return String, not &str
    let msg = String::from("Hello Rust!");
    msg
}
```

**Q3 Fix:**

```rust
fn main() {
    let nums = [1, 2, 3];
    for i in 0..nums.len() { // use .. not ..=
        println!("{}", nums[i]);
    }
}
```

---

### ✅ Section 4: Short Answers

**Q1.** `let` allows variable declaration, mutable if `mut` is used. `const` defines a compile-time constant and must always have a type.
**Q2.** Shadowing means redeclaring a variable with the same name, possibly changing type.

```rust
let x = 5;
let x = "hello"; // shadowing
```

**Q3.** Ownership defines which variable controls memory. Prevents double free, dangling pointers.
**Q4.** Rust strings are UTF-8 by default for internationalization and safety.
**Q5.**

```rust
fn even_or_odd(n: i32) -> &'static str {
    if n % 2 == 0 { "Even" } else { "Odd" }
}
```

---
