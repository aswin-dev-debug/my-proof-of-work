//loops

fn main(){ 
    // this program will never stop 
    // loop{
    //     println!("hi") // this never stops
    // }

    //example 1: simple loop
    let mut counter = 0; // set a counter to 0
    loop{
        counter +=1; //increase by 1
        println!("The counter is now:{}",counter);
        if counter == 5 { // stop when counter == 5
            break;
        }
    }

    //example 2: nested loop with labels
    let mut counter = 0;
    let mut counter2 = 0;
    println!("Now entering the first loop.");

    'first_loop:loop{
        //give the first loop a name
        counter += 1;
        println!("The counter is now:{}", counter);
        if counter > 9{
            // starts a second loop
            println!("Entering the second loop.");

            '_second_loop: loop {
                // in second loop
                println!("The second counter is now:{}",counter2);
                counter2 += 1;
                if counter2 == 3 {
                    break 'first_loop; // exits the first loop
                }
            }

        }
    }

    //example 3: while loop
    let mut counter = 0;
    while counter < 5{
        println!("The counter is now:{}",counter);
        counter +=1;
    }

    //example 4: for loop (exclusive range)
    for number in 0..3{ //exclusive range: 0..3 creates 0,1,2
        println!("The number is :{}",number);
    }

    //example 5: for loop (inclusive range)
    for number in 0..=3{//inclusive range 0..=3 = 0,1,2,3
        println!("The next number is:{}",number);
    }

    //example 6: break loop with value
    let mut counter = 5;
    let my_number = loop{
        counter +=1;
        if counter % 53 == 3{
            break counter;
        }
    };

    println!("The break value number is :{}",my_number);

    //example 7: match_colours usage
    let first =(200,0,0);
    let second =(50,50,50);
    let third =(200,50,0);

    match_colours(first);
    match_colours(second);
    match_colours(third);
}

fn match_colours(rbg:(i32,i32,i32)){
    println!("Comparing a colour with {} red, {} blue, and {} green:",rbg.0,rbg.1,rbg.2);
    let new_vec = vec![(rbg.0,"red"),(rbg.1,"blue"),(rbg.2,"green")];//colours in a vec inside the tuples
    let mut all_have_at_least_10 = true;

    for item in new_vec{
        if item.0 < 10{
            all_have_at_least_10 = false;
            println!("Not much {}.",item.1)
        }
    }

    if all_have_at_least_10{
        println!("Each colour has at least 10.")
    }

    println!();
}
