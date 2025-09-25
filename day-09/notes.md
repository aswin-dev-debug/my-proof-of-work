# Day 9 – Constants & Statics in Rust 🦀  

## 📘 What I Learned  
1. **`const`**  
   - Represents values that are **constant and known at compile-time**.  
   - Always written in **UPPERCASE** by convention.  
   - Example:  
     ```rust
     const MY_NUM: i8 = 8;
     const NUMBER_OF_MONTHS: u32 = 12;
     ```

2. **`static`**  
   - Represents a **global variable with a fixed memory address**.  
   - Useful for storing arrays or values that live for the **entire program duration**.  
   - Example:  
     ```rust
     static SEASONS: [&str; 4] = ["Spring", "Summer", "ASWIN", "BITOIN"];
     ```

3. **Key Difference**  
   - `const` = inlined wherever used (compile-time).  
   - `static` = stored in a fixed memory location (runtime).  

---

## 📝 Code  

```rust
// Global variables
const MY_NUM: i8 = 8; // Always uppercase by convention
const NUMBER_OF_MONTHS: u32 = 12;
static SEASONS: [&str; 4] = ["Spring", "Summer", "ASWIN", "BITOIN"];

fn main() {
    // Today I learned about const and static
    println!("{}", MY_NUM);
    println!("{}", NUMBER_OF_MONTHS);
    println!("{}", SEASONS[3]);
}
