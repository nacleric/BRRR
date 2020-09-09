# Error handling in Rust
[Error handling chapter](https://doc.rust-lang.org/book/ch09-00-error-handling.html)

Many built-in functions will return a Result type. This type will need to be error handled. Once the error has been handled it will become the type you were originally expecting.

Example situation:
`read_to_string()` returns a result type (needs error handling), and in that result type contains the actual string.

```Rust
// content is a Return type
let content = std:fs::read_to_string(&args.path);

// content becomes a String after error is unwrapped
let content = std::fs::read_to_string(&args.path).expect("could not read file");
```

## Unwrapping
let result is a Result type right now and it's being unwrapped in the match statement
```Rust
match result {
    Ok(content) => { println!("File content: {}", content); }
    Err(error) => { println!("Oh noes: {}", error); }
}
```

result is now assigned to content and we can use it outside of the match statement
```Rust
let content = match result {
    Ok(content) => content,
    Err(error) => {
        panic!("Can't deal with {}, just exit here", error);
    }
};
println!("file content: {}", content);
```
## Panic
Simplest form of error handling. `panic!("kill program")` will just stop the program
`.unwrap()` is just a match statement that returns `panic!("this will exit the program")` avoid using `unwrap`

## Option<T>
`Result<T>` is a more powerful version of Option<T> but rule of thumb is to use Result<T> when
your expecting to handle many types of errors and use Option<T> if you're handling 1 thing. (may
more may not return a value)

