# 🦀 Rust Learning Journey — Day 17: Control Flow (Part 2)

Today’s topic: **Advanced Control Flow with match and pattern bindings**

I explored how to use **match guards**, **pattern matching with tuples**, and **variable bindings (@)** inside `match` statements to handle complex logic in clean, expressive ways.

---

## 🧠 Concepts Covered

- Match guards with conditional checks inside pattern matches (`if` inside `match`)  
- Tuple pattern matching with RGB color values  
- Using `@` (pattern binding) to capture matched values  
- Scoping variables inside `if` and `else` blocks  

---

## 🧩 Code Example

```rust
// Control Flow Part - 2

fn match_colours(rgb: (i32, i32, i32)) {
    match rgb {
        (r, _, _) if r < 10 => println!("Not much red"),
        (_, g, _) if g < 10 => println!("Not much green"),
        (_, _, b) if b < 10 => println!("Not much blue"),
        _ => println!("Each colour has at least 10"),
    }
}

fn match_number(input: i32) {
    match input {
        number @ 4 => println!("{} is an unlucky number in China", number),
        number @ 13 => println!("{} is unlucky in North America, lucky in Italy", number),
        _ => println!("Looks like a normal number"),
    }
}

fn main() {
    let first = (200, 0, 0);
    let second = (50, 50, 50);
    let third = (200, 50, 0);

    match_colours(first);
    match_colours(second);
    match_colours(third);

    let my_number = 10;
    if my_number == 10 {
        let some_variable = 8;
        println!("My number is 10 → {}", some_variable);
    } else {
        let some_variable = "Something else";
        println!("{}", some_variable);
    }

    match_number(50);
    match_number(13);
    match_number(4);
}
