# 🦀 Day 21 — Structs, Enums & Methods in Rust

Today’s learning focused on **structs**, **enums**, and **implementations (`impl`)** in Rust.  
I explored how to:

- Define a struct with `#[derive(Debug)]`
- Create and modify struct instances
- Use `enum` with `match`
- Add methods using `impl` blocks

---

## 🧱 Struct and Enum Example

```rust
// Define a struct with #[derive(Debug)]
#[derive(Debug)]
struct User {
    username: String,
    email: String,
    active: bool,
    sign_in_count: u64,
}

// Define an enum
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}

// Implement methods for the struct
impl User {
    fn new(username: String, email: String) -> Self {
        Self {
            username,
            email,
            active: true,
            sign_in_count: 1,
        }
    }

    fn deactivate(&mut self) {
        self.active = false;
    }

    fn display(&self) {
        println!("User Info: {:?}", self);
    }
}

fn main() {
    let mut user1 = User::new(
        String::from("rustacean"),
        String::from("rustacean@example.com"),
    );

    user1.display();
    user1.deactivate();

    let msg = Message::Move { x: 10, y: 20 };

    match msg {
        Message::Quit => println!("Quit message received."),
        Message::Move { x, y } => println!("Move to position: ({x}, {y})"),
        Message::Write(text) => println!("Message: {text}"),
        Message::ChangeColor(r, g, b) => println!("Change color to RGB({r}, {g}, {b})"),
    }
}
