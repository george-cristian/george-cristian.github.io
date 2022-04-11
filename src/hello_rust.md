# Demo - Hello Rust


A guessing game made with Rust, in which a random number is generated between 1 and 100, and the user has to input a guess. The program will signal if the guess is high or low, and the user can try again until it's perfect.
```rust
use std::io;
use rand::Rng;
use std::cmp::Ordering;

fn main() {
    println!("Guess the number!");
    
    // generate a random number from 1 to 100
    let secret_number = rand::thread_rng().gen_range(1..101);
    
    // loop until a perfect guess is made
    loop {
        println!("Please input your guess");

        let mut guess = String::new();

        io::stdin().read_line(&mut guess)
            .expect("Failed to read line");

        println!("You guessed: {}", guess);

        let guess: u32 = match guess.trim().parse() {
            Ok(num) => num,
            Err(_) => continue
        };

        match guess.cmp(&secret_number) {
            Ordering::Less => println!("Too small!!!"),
            Ordering::Greater => println!("Too big!!!"),
            Ordering::Equal => {
                println!("Perfect!!!");
                break;
            }
        }
    }
}

```
The code above, depends on the external library _"rand"_. In order to instruct the Rust build system to fetch this external library, the following should be present in the _Cargo.toml_ file:
```toml
[dependencies]
rand = "0.8.5"
```