# Rough Rust notes

## String stuff
String owned 
str borrowed 

## Borrow checker
T is owned 
&T is shared (many can access) 
&mut T is exclusive (only 1) 

### Good version
https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=ce3af210ecac2b9bdeb5157e5e26ba22 

### Better version
https://play.rust-lang.org/?version=stable&mode=debug&edition=2018&gist=d49b99987d8e0625599c5e8b5b40e885 


copy only copys the header(pointers, len, size) but it points to the same location on the heap 

heap based bindings
