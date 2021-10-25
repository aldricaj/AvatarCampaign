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

#### Creating a new project w/ Cargo
`cargo new $projectName` creates a new folder w/ name $projectName

Creates a project with a `cargo.toml` and a src directory w/ a default main file. It also creates a git repo

`cargo build` builds the project. `cargo build --release` compiles the project for a release configuration. This includes a number of optimizations. Binaries are dumped in `target/debug` for noargs build and in `target/release`.

`cargo run` builds then runs the project

`cargo check` verifies program but doesn't produce an executable and is generally faster



##### Anatomy of TOML file
`package` heading marks the package's metadata
`dependencies` heading marks dependencies required for the project