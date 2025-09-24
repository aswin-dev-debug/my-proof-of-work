# Day 8 – Strings, UTF-8 & `format!` in Rust 🦀  

## 📘 What I Learned  
1. **Difference between `&str` and `String`**  
   - `&str` → String slice, very fast, immutable, used for literals.  
   - `String` → Heap-allocated, slower but flexible (can be mutated, grown).  

2. **UTF-8 Compatibility**  
   - Rust’s strings are UTF-8 encoded.  
   - Handles characters like Korean (`서태지`) or Romanian (`Țepeș`) without issues.  

3. **`format!` Macro**  
   - Works like `println!` but instead of printing, it **returns a formatted String**.  

4. **Converting into `String`**  
   - Example: `"Try to make a string".into()` converts a string slice into a `String`.  

---

## 📝 Code  

```rust
fn main() {
    let _my_variable = "Hello, world";
    // &str → Fast string slice
    // String → Structured, heap-allocated

    let name = "서태지"; // Korean name in UTF-8
    let other_name = String::from("Adrian Fahrenheit Țepeș"); // Romanian UTF-8
    println!("{} is {}", name, other_name);

    // Using format! macro
    let my_name = "ASHU";
    let my_country = "India";
    let my_home = "Tamil Nadu";

    let together = format!(
        "I am {} and I come from {} but I live in {}",
        my_name, my_country, my_home
    );
    println!("{}", together);

    // Converting into String
    let my_string: String = "Try to make a string".into();
}

https://gist.github.com/rust-play/602ca0b8b3d4fd6c0d3af9a4b82ff650 (rust coding page link)
