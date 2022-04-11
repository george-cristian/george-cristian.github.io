# The Rust Environment

### The development ecosystem
* Easy to install (as you will see)
* Comes with a friendly compiler
* Offers dependency/package management system (via Cargo, explained below)
* Comes with a built-in unit testing framework
* Built-in documentation generation


### Cargo
What does it do?
* Package manager
* Build system
* Fetches and builds dependencies
* Compiles packages

It can be used to also set up a new project. Examples of usage:
* To create a new project (this command also generates: a Cargo configuration TOML file + a main.rs file + initializes a new Git repository):
```shell
cargo new hello_world
```
* To build the project:
```shell
cd hello_world
cargo build
```
* To build and run the project:
```shell
cargo run
```

Cargo comes installed with Rust, out of the box. And it is configured using a file called _Cargo.toml_ which is generated when a new project is set up. A simple _Cargo.toml_ file looks like this:
```toml
[package]
name = "example_project"
version = "0.1.0"
edition = "2018"
authors = ["Example Project <example@project.com"]

[dependencies]
rand = "0.8.5"
```