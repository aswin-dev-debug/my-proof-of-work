# Day 5 – Mutability, Shadowing, and Debug Print in Rust 🦀

## 📌 What I Learned
- Code blocks `{}` can return values (like functions).
- Traits give “powers” to types (e.g., `Display`, `Debug`).
- `println!("{:?}", var)` works for debugging.
- `mut` makes variables mutable (can change).
- Shadowing allows reusing the same variable name with new values or even new data types.
- Shadowing works in inner blocks without destroying outer variables.

---

## 📝 Example Code

```rust
fn main() {
    let my_number = {
        let second_number = 8;
            second_number + 9; // no semilcolon, so the code block returns 8+9
                               // it works just like a function
    };
    //: `()` doesn't implement `std::fmt::Display`
    // () does not have the power of 'Display'
    //trait = powers of types
    
    println!("My number is {:?}",my_number);//noe this only  {:?}` (or {:# } pretty-instead my understanding this works as debug
    
    
    //Mutabililty
    
    let mut my_number = 8; // add mut that can change mutability 
    println!("My number is :{}",my_number);
    my_number = 10;  
    println!("Now my number is: {}",my_number);
    
    // shadowing
    
    let my_number = 8; // add mut that can change mutability without adding a let in anpther variable
    println!("My number is :{}",my_number);
    let my_number = "Rust developer"; // adding a let this changes like assigning new vaiable to the same variable able to use another dt like string
    println!("Now my number is: {}",my_number);
    
    //another example
    
    let my_number = 8; //this is i32
    println!("{}",my_number);//prints 8
    {
        let my_number = 9.2; //this is an f64.it is not my_number - it is completely different;
        println!("{}",my_number)//prints 9.2
                                // but the shadowed my_number only lives until here.
                                // the first  my-number is still alive!
    };
    
     println!("{}",my_number);//prints 8
     // you dont destroy it, just block it it s a shadowing i like this line
     
    //another example
    let final_number={
        let y = 10;
        let x = 9;// x starts at 9
        let x = times_two(x);//shadow with new x: 28
        let x = x+y; // shadowing with new x : 28
        x // return x: final_number is now the value of x
    };
    println!("the number is now : {}",final_number)
    
}

fn times_two(number: i32) -> i32{
    number * 2
}
