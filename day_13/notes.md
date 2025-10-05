# Day 13 – Arrays and Slicing in Rust

## 📘 What I Learned Today
- Arrays in Rust are **fixed-size collections** that store elements of the same type.  
- The type of an array includes its length, e.g.:
  - `["One", "Two"]` → ` [&str; 2]`
  - `["One", "Two", "Six"]` → `[&str; 3]`
- You can create repeated arrays like:  
  `let my_array = ["India"; 10];` → creates 10 copies of `"India"`.
- Arrays can store numbers too:  
  `let my_numbers = [0, 10, 20, -20];`

---

## 🔪 Slicing in Rust
- You can access **parts of arrays** using slices:  
  - `&array[start..end]` → elements from index `start` (inclusive) to `end` (exclusive).
- Examples:
  ```rust
  let array_of_ten = [1,2,3,4,5,6,7,8,9,10];

  let three_to_five = &array_of_ten[2..5];   // [3, 4, 5]
  let start_at_two = &array_of_ten[1..];     // [2..10]
  let end_at_five   = &array_of_ten[..5];    // [1, 2, 3, 4, 5]
  let everything    = &array_of_ten[..];     // whole array
