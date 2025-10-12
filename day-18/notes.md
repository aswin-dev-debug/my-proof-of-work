# 🦀 Rust Learning Journey — Day 18: Structs (Structures)

Today I learned about **structs** in Rust — how to define, initialize, and use them effectively.  
Structs are powerful for organizing and grouping related data in Rust programs.

---

## 🧠 Concepts Covered

- `struct` keyword and **naming conventions** (UpperCamelCase)
- **3 types of structs**:
  1. **Unit Structs** — have no data, used as markers or placeholders
  2. **Tuple Structs** — unnamed fields, access via indexes
  3. **Named Structs** — most common form, use named fields for clarity
- Using `#[derive(Debug)]` to print struct data with `{:?}`
- Nesting structs within other structs
- Example of creating a real-world structure (`Country`)

---

## 🧩 Code Example

```rust
// Structure — Structs

// 1️⃣ Unit Struct
struct FileDirectory;

// 2️⃣ Tuple Struct — unnamed fields
#[derive(Debug)]
struct Colour(u8, u8, u8);

// 3️⃣ Named Struct — most common form
#[derive(Debug)]
struct SizeAndColour {
    size: u32,
    colour: Colour, // Nested struct
}

// Example: A struct representing a country
#[derive(Debug)]
struct Country {
    population: u32,
    capital: String,
    president_name: String,
}

fn main() {
    let my_colour = Colour(50, 0, 50);
    println!("The second of the colour is: {}", my_colour.1);

    let size_and_colour = SizeAndColour {
        size: 150,
        colour: my_colour,
    };

    println!("{:?}", size_and_colour);

    let population = 500_000;
    let capital = String::from("Delhi");
    let president_name = String::from("Droupadi Murmu");

    let INDIA = Country {
        population,
        capital,
        president_name,
    };
    
    println!("{:?}", INDIA);
}
