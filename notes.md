# Rust Notes

## Chapter 1
To compile: `rustc $filePath`

Function defined through: `fn foo_bar() {}`. Style dictates that opening brace on same line as func def

`println!` is a macro as signified by the bang. The bang differentiates between a macro and a function

Rust compiles to native code

### Cargo

Cargo == Rust build system/package manager. Similar to NPM

Use of Cargo is implied in book

`cargo --version` shows version of cargo installed

`cargo update` updates packages


#### Creating a new project w/ Cargo
`cargo new $projectName` creates a new folder w/ name $projectName

Creates a project with a `cargo.toml` and a src directory w/ a default main file. It also creates a git repo

`cargo build` builds the project. `cargo build --release` compiles the project for a release configuration. This includes a number of optimizations. Binaries are dumped in `target/debug` for noargs build and in `target/release`.

`cargo run` builds then runs the project

`cargo check` verifies program but doesn't produce an executable and is generally faster



##### Anatomy of TOML file
`package` heading marks the package's metadata
`dependencies` heading marks dependencies required for the project

## Chapter 2: Programming a guessing game

### Syntax
`use std::io` imports io from the std library

`let mut guess = String::new();` does a bit. 
- `let mut` declares a mutable variable (one that can be change).
- `String::new()` declares a new empty string. 

`bar::foo()` calls foo which is an associated function of bar

`foo(&bar)` passes bar as a reference to foo instead of by value. Use `&mut bar` to make bar mutable in the called function

`.expect('string')` handles a returned `io::Result` return type. A Result has two values `Ok` and `Error`. If `Error` is returned, expect will print the string passed to it and kill the process

`println!("string {} {}", foo, bar)` prints out `string $foo $bar`. 

#### Mutability
By default all variable are immutable. This means they can't be changed

#### Match syntax
`match` works similarly to a switch statement a full block looks like:
```
match expr {
  option => val,
  option2 => val2,
}
  ```

### Crates
A crate is a package

To add a crate as a dependency add it to the `[dependency]` section of the cargo.toml file. Entered as `crate = "0.0.0"` where 0.0.0 is the version
