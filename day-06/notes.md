# Day 6 – Stack vs Heap, References in Rust 🦀

## 📌 What I Learned
- The stack is very fast, but you can’t always use it.
- Rust wants to know the size of variables at compile time.
- The heap can take any kind of variable, store it as a pointer, and then move a reference to the stack.
- Computer first checks the stack → then follows the pointer → which points to the heap.
- Learned how `&` and `*` work with references and dereferencing.

---

## 📝 Example Code

```rust
fn main() {
    //the stack is very fast but heap is not fast but you cant use stack all the time
    //reason rust wants to know the size of the variable
    //the idea is heap take a any kind of varible and make as pointer and after that move stack
    //the pointer have a size of the variable and after the commputer first goes tot the stack and reads the points and where heap allows

    let my_num = 8;
    let my_ref = &&my_num;

    println!("{}", my_num == **my_ref);

    // & = *
    // && = ** for sake of printing and calling in macro function
}
