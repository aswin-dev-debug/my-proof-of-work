# Rust Basics - Day 7 🦀  
Today’s focus was on **strings, escape sequences, raw strings, and Unicode handling** in Rust.  

---

## 📘 Key Learnings
1. **Multi-line strings** – you can write text over many lines inside quotes.  
2. **Escape characters** –  
   - `\n` → new line  
   - `\t` → tab  
   - `\\` → backslash  
3. **Raw strings** – use `r#""#` to avoid escaping characters.  
   - Add more `#` symbols if the content itself has `#`.  
4. **Unicode handling** – cast chars to `u32` and print in hex (`{:X}`).  
5. **Unicode escapes** – `\u{XXXX}` lets you print characters directly.  

---

## 🧑‍💻 Example Code
```rust
fn main() {
    // Multi-line string
    println!("Inside quotes
you can write over
many lines
and it will print just fine.");

    // Leading spaces preserved if not aligned
    println!("If you forget to write
    on the left side, the spaces
    will be added when you print.");

    // Escape characters
    println!("Here are two escape characters: \\n and \\t");

    // Escaping quotes and paths
    println!("He said, \"You can find the file at c:\\files\\my_documents\\file.txt.\"");

    // Raw strings (no need to escape)
    println!(r#"He said, "You can find the file at c:\files\my_documents\file.txt."#);

    // Raw strings with different levels of #
    let my_string = "'Ice to see you,' he said."; 
    let quote_string = r#""Ice to see you," he said."#;
    let hashtag_string = r##"The hashtag #IceToSeeYou had become very popular."##;
    let many_hashtags = r####""You don't have to type ### to use a hashtag. You can just use #.""####;

    println!("{}\n{}\n{}\n{}\n", my_string, quote_string, hashtag_string, many_hashtags);

    // Unicode as hex
    println!("{:X}", '행' as u32);
    println!("{:X}", 'H' as u32);
    println!("{:X}", '居' as u32);
    println!("{:X}", 'い' as u32);

    // Printing Unicode with escape sequences
    println!("\u{D589}, \u{48}, \u{5C45}, \u{3044}");
}
