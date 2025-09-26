# Day 10 – Ownership & References in Rust 🦀  

## 📘 What I Learned  
1. **Ownership**  
   - Every value in Rust has a single **owner**.  
   - When the owner goes out of scope, the value is dropped (memory freed).  

2. **References (`&`)**  
   - You can have multiple immutable references to a variable.  
   - Example:  
     ```rust
     let ref_one = &country;
     let ref_two = &country;
     ```

3. **Returning Values & Ownership**  
   - Returning a `String` from a function transfers ownership back to the caller.  
   - Example:  
     ```rust
     fn return_str() -> String {
         let country = String::from("India");
         country // Ownership is moved out
     }
     ```

---

## 📝 Code  

```rust
fn return_str() -> String {
    let country = String::from("India");
    // Tried referencing here – didn’t work, because of Rust’s ownership rules.
    country // Ownership returned to the caller
}

fn main() {
    // OWNERSHIP = who owns a value
    let country = String::from("India");

    let ref_one = &country;
    let ref_two = &country;

    let country2 = return_str();

    println!("{},{},{}", country, ref_one, ref_two);
    println!("from outside scope: {}", country2);
}


link::https://gist.github.com/rust-play/eac8ca19c386eb16ae313e3c9fdfb975
