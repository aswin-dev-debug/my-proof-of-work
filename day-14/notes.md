# 🦀 Rust Learning Journey — Day 14: Vectors

Today’s topic: **Vectors in Rust**

I learned how vectors work — how to create them, push values dynamically, slice them like arrays, and manage their memory capacity efficiently.

---

## 🧠 Concepts Covered

- Declaring vectors using `Vec::new()` and `vec![]`
- Adding elements using `.push()`
- Using `Vec::with_capacity()` to control memory allocation
- Slicing vectors with ranges (`[start..end]`)
- Using `.into()` to convert arrays into vectors
- Understanding reallocation and capacity growth

---

## 🧩 Code Example

```rust
// Vectors in Rust

fn main() {
    let name1 = String::from("Arun");
    let name2 = String::from("Kams");

    // Declaring an empty vector with an explicit type
    let mut my_vec: Vec<String> = Vec::new();

    my_vec.push(name1);
    my_vec.push(name2);

    // vec! is a macro for quick initialization
    let my_vec = vec![8, 10, 10];
    println!("{:?}", my_vec);

    // Demonstrating slicing operations on vectors
    let vec_of_ten = vec![1,2,3,4,5,6,7,8,9,10];

    let three_to_five = &vec_of_ten[2..5];
    let start_at_two = &vec_of_ten[1..];
    let end_at_five = &vec_of_ten[..5];
    let everything = &vec_of_ten[..];

    println!(
        "Three to five: {:?}\nStart at two: {:?}\nEnd at five: {:?}\nEverything: {:?}",
        three_to_five, start_at_two, end_at_five, everything
    );

    // Demonstrating capacity growth
    let mut num_vec = Vec::with_capacity(8);
    println!("Initial capacity: {}", num_vec.capacity());

    num_vec.push('a');
    println!("After 1 push: {}", num_vec.capacity());
    num_vec.push('a');
    println!("After 2 pushes: {}", num_vec.capacity());
    num_vec.push('a');
    println!("After 3 pushes: {}", num_vec.capacity());
    num_vec.push('a');
    println!("After 4 pushes: {}", num_vec.capacity());
    num_vec.push('a');
    println!("After 5 pushes: {}", num_vec.capacity());

    // Using .into() to convert arrays into vectors
    let my_vec2: Vec<_> = [9, 0, 10].into();
    println!("Converted using .into(): {:?}", my_vec2);
}
