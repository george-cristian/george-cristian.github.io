# Setting Up The Environment

## Installing Rust on Windows

Go to the following link and follow the instructions for installation: <https://www.rust-lang.org/tools/install>

Rust also requires the C++ build tools. In case you do not have those, you can get them via this link: <https://visualstudio.microsoft.com/visual-cpp-build-tools/>

## Installing Rust on Linux or macOS
The following command downloads and installs the latest stable version of Rust:
```shell
curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```
Rust also needs a C compiler. In case you do not have one, do the following:
* For **Linux**
```shell
sudo apt-get update
sudo apt install build-essential
```
* For **macOS**
```shell
xcode-select install
```

## What IDEs can be used?
Mainly for syntax highlighting, code completion, etc. Both have Rust plugins:
* Visual Studio Code
* IntelliJ IDEA