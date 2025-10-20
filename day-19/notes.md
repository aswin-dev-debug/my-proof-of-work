// enum
// struct -- AND
// enum   -- OR

// Example 1: Create enum with two choices
// enum ThingsInTheSky{
//     Sun,
//     Stars, // the sun or stars i want to choose one that is called variants
// }

// // with this function we can use an i32 to create ThingsInTheSky
// fn create_skystate(time: i32) -> ThingsInTheSky {
//     match time {
//         6..=18 => ThingsInTheSky::Sun,//between 6 and 18 hrs we can see the sun
//         _=> ThingsInTheSky::Stars, // otherwise we can see the stars
//     }
// }

// // with this we can match against the two choices in ThingsInTheSky
// fn check_skystate(state: &ThingsInTheSky){
//     match state {
//         ThingsInTheSky::Sun => println!("I can see the sun!"),
//         ThingsInTheSky::Stars => println!("I can see the stars!")
//     }
// }

// Now try with strings

enum ThingsInTheSky {
    Sun(String),
    Stars(String),
}

// With this function we can use an i32 to create ThingsInTheSky
fn create_skystate(time: i32) -> ThingsInTheSky {
    match time {
        6..=18 => ThingsInTheSky::Sun(String::from("I can see the sun!")),
        _ => ThingsInTheSky::Stars(String::from("I can see the stars!")),
    }
}

// Match against the two choices in ThingsInTheSky
fn check_skystate(state: &ThingsInTheSky) {
    match state {
        ThingsInTheSky::Sun(description) => println!("{}", description),
        ThingsInTheSky::Stars(n) => println!("{}", n),
    }
}

// Another example with Mood
enum Mood {
    Happy,
    Sleepy,
    NotBad,
    Angry,
}

fn match_mood(mood: &Mood) -> i32 {
    use Mood::*;
    match mood {
        Happy => 10,
        Sleepy => 6,
        NotBad => 7,
        Angry => 2,
    }
}

// Another example: Season
enum Season {
    Spring,
    Summer,
    Autumn,
    Winter,
}

// Another example: Star with values
enum Star {
    BrownDwarf = 10,
    RedDwarf = 50,
    YellowStar = 100,
    RedGiant = 1000,
    DeadStar, // Think about this one. What number will it have??
}

// Another example: Enum that stores numbers
enum Number {
    U32(u32),
    I32(i32),
}

fn get_number(input: i32) -> Number {
    let number = match input.is_positive() {
        true => Number::U32(input as u32),
        false => Number::I32(input),
    };
    number
}

fn main() {
    let time = 5; // it's 5 o'clock
    let skystate = create_skystate(time); // create_skystate returns a ThingsInTheSky
    check_skystate(&skystate);

    // Another example: Mood
    let my_mood = Mood::NotBad;
    let happiness_level = match_mood(&my_mood);
    println!("Out of 1 to 10, my happiness is {}", happiness_level);

    // Another example: Seasons
    use Season::*;
    let four_seasons = vec![Spring, Summer, Autumn, Winter];
    for season in four_seasons {
        println!("{}", season as u32);
    }

    // Another example: Stars
    use Star::*;
    let starvec = vec![BrownDwarf, RedDwarf, YellowStar, RedGiant];
    for star in starvec {
        match star as u32 {
            size if size <= 80 => println!("Not the biggest star."),
            size if size >= 80 => println!("This is a good-sized star."),
            _ => println!("That star is pretty big!"),
        }
    }

    println!("What about DeadStar? Its number is {}.", DeadStar as u32);

    // Another example: Numbers
    let my_vec = vec![get_number(-800), get_number(8)];

    for item in my_vec {
        match item {
            Number::U32(n) => println!("It's a u32 with the value {}", n),
            Number::I32(number) => println!("It's an i32 with the value {}", number),
        }
    }
}
