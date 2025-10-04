# Day 12 – Copy Trait, Clone, and Initialization

## 📘 What I Learned Today
- **Copy trait**:
  - Primitive types like `i32` implement the `Copy` trait.
  - This means they can be reused after being passed into a function (ownership is not moved).

- **Clone**:
  - Heap-allocated types like `String` don’t implement `Copy`.
  - To reuse them, you must explicitly call `.clone()`.
  - `clone()` makes a deep copy and usually takes more memory.

- **Initialization in Rust**:
  - Variables can be declared outside a block and then initialized inside.
  - Rust ensures that every variable must be initialized before it is used.

---

## 📝 Code Example

```rust
// Copy trait
fn prints_number(number: i32) {
    println!("{}", number);
}

fn prints_country(country_name: String) {
    println!("{}", country_name);
}

fn main() {
    let my_number = 8;
    prints_number(my_number); // prints 8
    prints_number(my_number); // prints 8 again → Copy works

    let country = String::from("India");

    // String doesn't have Copy trait, so use clone
    prints_country(country.clone());
    // prints_country(country); // ❌ won't work (ownership moved)
    prints_country(country.clone());
    prints_country(country); // ✅ ownership finally moved

    // Initialization inside block
    let my_numbers;
    { 
        // Pretend we need this block for setup
        my_numbers = 57; 
    }
    println!("{}", my_numbers); // 57
}
