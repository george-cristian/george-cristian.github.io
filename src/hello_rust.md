# Demo - Hello Rust


The following is a guessing game made with Rust, in which a random number is generated between 1 and 100, and the user has to input a guess. The program will signal if the guess is high or low, and the user can try again until it's perfect.

First, set up a new project, using Cargo:
```shell
cargo new guessing_game
cd guessing_game
```

* Inside the new folder, a _Cargo.toml_ file is generated which basically configures your program (as explained in [Chapter 1](environment.html)). Update it as you please.
* And also a _src_ folder is generated with a file inside called _main.rs_ which contains a "Hello World!" program (you can compile and run it, as explained in [Chapter 1](environment.html))


Enter the following piece of code inside the _main.rs_ file:

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

Compile and run the program as explained in [Chapter 1](environment.html). Have fun!