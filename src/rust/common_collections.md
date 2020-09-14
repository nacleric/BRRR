# Collections 
[Chapter 8 link](https://doc.rust-lang.org/book/ch08-00-common-collections.html) 

Rust's standard library includes a number of very useful data structures called collections. Most other data types represent one specific value, but collections can contain multiple values. Unlike the built-in array and tuple types, the data these collections point to is stored on the heap, which means the amount of data does not need to be known at compile time and can grow or shrink as the program runs. Each kind of collection has different capabilities and costs, and choosing an appropriate one for your current situation is a skill you’ll develop over time. 

- A vector allows you to store a variable number of values next to each other.
- A string is a collection of characters. We've mentioned the String type previously, but in this chapter we’ll talk about it in depth.
- A hash map allows you to associate a value with a particular key. It’s a particular implementation of the more general data structure called a map.

## Vector examples
The first collection type we’ll look at is Vec<T>, also known as a vector. Vectors allow you to store more than one value in a single data structure that puts all the values next to each other in memory. Vectors can only store values of the same type. They are useful when you have a list of items, such as the lines of text in a file or the prices of items in a shopping cart.

Note: Remember to use `#[derive(Debug)]` when printing to console 

[Vector playground](https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=0cd1df994bea1cd9884f198ddf2c9905) 

## Hashmap examples
The last of our common collections is the hash map. The type HashMap<K, V> stores a mapping of keys of type K to values of type V. It does this via a hashing function, which determines how it places these keys and values into memory. Many programming languages support this kind of data structure, but they often use a different name, such as hash, map, object, hash table, dictionary, or associative array, just to name a few. 

[Hashmap playground](https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=e4b787dada5bc813b0ef62e09678c833) 
