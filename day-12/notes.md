//copy trait

fn prints_number(number: i32){
    println!("{}",number);
}

fn main(){
    let my_number = 8;
    prints_number(my_number);// prints 8
    prints_number(my_number);// prints 8 again and copy trait works
    
    let country = String::from("India");
    prints_country(country.clone());
    //prints_country(country);//this is not works becaise of the string type
    prints_country(country.clone());
    prints_country(country);
    //learned about the intialization of rust 
    let my_numbers;
       { // Pretend we need to have this code block
        my_numbers = 
            // Pretend there is code here to make a number
            // Lots of code, and finally:
            57;
        }

    println!("{}", my_numbers);
}

//In this copy not works is works on the cloneand usually need more memory

fn prints_country(country_name: String){
    println!("{}",country_name);
}



