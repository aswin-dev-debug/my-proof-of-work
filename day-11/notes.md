# Day 11 – Mutable References & Shadowing in Rust 🦀  

## 📘 What I Learned  
1. **Mutable References (`&mut`)**  
   - You can modify values through mutable references.  
   - Example:  
     ```rust
     let mut my_number = 8;
     let num_ref = &mut my_number;
     *num_ref += 10;
     println!("{}", my_number); // 18
     ```

2. **Immutable vs Mutable References**  
   - You can’t mix multiple mutable references at the same time.  
   - But you can borrow immutably after a mutable borrow ends.  
   - Example:  
     ```rust
     let mut number = 10;
     let number_change = &mut number;
     *number_change += 10; // 20
     let number_ref = &number; // immutable borrow works after mutation
     println!("{}", number_ref);
     ```

3. **Shadowing**  
   - A variable name can be reused (shadowed) with a new value or type.  
   - Example:  
     ```rust
     let country = String::from("Austria");
     let country_ref = &country;
     let country = 8; // shadows the string variable
     println!("{},{}", country_ref, country);
     ```

4. **Passing References to Functions**  
   - Functions can take references to avoid ownership transfer.  
   - Example:  
     ```rust
     fn print_country(country_name: &String) {
         println!("{}", country_name);
     }

     let country = String::from("Austria");
     print_country(&country);
     print_country(&country);
     ```

---

## 📝 Code  

```rust
// MUTABLE REFERENCES WITH &mut

fn print_country(country_name: &String) { // references via functions
    println!("{}", country_name);
}

fn main() {
    let mut my_number = 8; // mut gives only that takes mutable
    let num_ref = &mut my_number;

    *num_ref += 10;
    println!("{}", my_number);

    // another example
    let mut number = 10;
    let number_change = &mut number;
    *number_change += 10;
    let number_ref = &number;
    println!("{}", number_ref);

    // shadowing
    let country = String::from("Austria");
    let country_ref = &country;
    let country = 8;
    println!("{},{}", country_ref, country);

    // functions calling
    let country = String::from("Austria");
    print_country(&country);
    print_country(&country);
}
