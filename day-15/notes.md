# 🦀 Rust Learning Journey — Day 15: Tuples

Today’s topic: **Tuples in Rust**

I explored how tuples work — a versatile data structure that can hold values of different types together, and how destructuring helps extract values efficiently.

---

## 🧠 Concepts Covered

- Creating tuples with mixed data types  
- Accessing tuple elements using dot (`.`) notation  
- Destructuring tuples into individual variables  
- Using `_` to ignore specific values while destructuring  

---

## 🧩 Code Example

```rust
// Tuples in Rust

fn main() {
    // A tuple holding multiple data types
    let random_tuple = ("Aswin", 8, vec!['a'], 'b', [8, 9, 10], 7.7);

    // Accessing elements using dot notation
    println!(
        "Name: {:?}\nSecond item: {:?}\nFourth item: {:?}\nFifth item: {:?}",
        random_tuple.0, random_tuple.1, random_tuple.3, random_tuple.4
    );

    // Destructuring (pulling apart tuple or data structure)
    let str_vec = vec!["one", "two", "three"];

    // Destructuring into individual variables
    let (a, b, c) = (str_vec[0], str_vec[1], str_vec[2]);
    println!("{:?}", b);

    // If you want to skip variables during destructuring, use '_'
}

rust code:https://gist.github.com/rust-play/19de3cecdc873675a002f0c04b3d0170
