# Short Introduction to Rust

### What is Rust?

* Open Source, cross-platform, compiled language
* Focus on memory/thread safety
* No need for runtime
* Support for bare metal
* Built-in infrastructure
* Interoperable with C

### Some core features
* Low level language -> Compiles to machine code
* Zero-cost abstraction
* Borrow checker
* Powerful enums
* Etc. 

### Comparison against other languages
* C++ 
  * No segfaults/buffer overflows/null pointers/data races/uninitialized data in Rust
  * Rust has a built-in dependency management/build system (aka cargo)
  * Friendly compiler errors in Rust
  * Threads without data races in Rust
* Java
  * No Garbage Collector in Rust and no runtime -> Lower memory use and overhead
  * No JVM (bytecode interpretation) and no JIT overhead in Rust -> Rust uses LLVM (native code)
  * Zero-cost abstraction
* Python
  * Rust is much faster
  * No Garbage Collector in Rust
  * Multithreading without pain in Rust
  * Static vs Dynamic typed

For more detailed info, check the official Rust documentation: <https://doc.rust-lang.org/stable/book/foreword.html>