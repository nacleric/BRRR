# Enums
Enums are sum-types. Number of different states are added by the number of fields
```
#[derive(Debug)]
enum IpAddrKind {
    V4,
    V6,
}
```
- There can only be 2 possible states for this enum hence sum-type
- Enums are great with match statements, can do pattern matching with them

#  Structs
Structs are product-types, number of states is a multiple of the number of fields
```
#[derive(Debug)]
struct User {
  username: String,
  email: String,
  sign_in_count: u64,
  active: bool,
}
```

## Non-accurate descriptions Adaefsas
- Enum contains "variants", can only ever be 1, Ex: V6 can never be V4
- Structs contain fields and are meant to represent something. Enums are constrained
