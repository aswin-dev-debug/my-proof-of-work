#[derive(Debug)]

struct Person{
    name: String,
    real_name: String,
    height:u8,
    happiness: bool
}

//another example
struct City{
    name: String,
    name_before: String,
    population: u32,
    date_founded: u32,
}

impl City{
    fn new(name: String,name_before: String, population: u32, date_founded: u32) -> Self{
        Self {
            name,
            name_before,
            population,
            date_founded
        }
    }
}

fn process_city_values(city: &City){
    let City{
        name,
        name_before,
        population,
        date_founded
    } = city;

    let two_names = vec![name,name_before];
    println!("The city's two names are {:?}",two_names);
}


fn main(){
    let papa_doc= Person{
        name: "Papa Doc".to_string(),
        real_name:"father".to_string(),
        height:60,
        happiness:false
    };

    let Person {
        name:a,
        real_name: b,
        ..
    } = papa_doc;

    println!("{} {}",a,b);

    //another example

    let tallinn = City::new("Tallinn".to_string(),"Aswin".to_string(),4376,1154   );
    process_city_values(&tallinn);
}
