# Common Datatypes in Rust

## The different strings in Rust
`String` is an owned typed 
`&str` is a borrowed typed 

General Rule: Prefer &str as a function parameter or if you want a read-only view of a string; String when you want to own and mutate a string 

[More info](https://www.ameyalokare.com/rust/2017/10/12/rust-str-vs-String.html)
