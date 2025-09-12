
fn main() {
    
    println!("Hello, rust!");
    //Practice the types
    let slice = "Hello!";
    println!("Slice is {} bytes.", slice.len());
    let first_letter = "A";
    println!("Fisrt letter is {} bytes.",first_letter.len());
    let space = " "; //space inside ' 'is alse char
    println!("Fisrt letter is {} bytes.",space.len());
    let other_language_char ="வணக்கம்";  //hello in  tamil
    println!("Fisrt letter is {} bytes.",other_language_char.len());
    let cat_face = "👍";
     println!("Emoji is {} bytes.",cat_face.len());
     println!("other_Languages is {} bytes but only {} characters.", other_language_char.len(), other_language_char.chars().count());
    
    //Type inference
    let small_number  = "10";
    // let change = small_number as char;
    // println!("{}",)
    println!("small_number {}",small_number.len());
    
    let number =0_____u8;
    let num2 = 1___2__i32;
    println!("{},{}",number,num2);
    
}
