> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Introduction

Rust has two [data type subsets](https://doc.rust-lang.org/book/ch03-02-data-types.html), scalar, and compound. The scalar types are integers, floating numbers, Booleans, and characters. The compound types are arrays and tuples.

In this article we are going to see why the following code fails:

```rust
// When we operate different data types, it fails:
fn main() {
    let a: i16 = 2;
    let b: u16 = 4;
    println!("{}", a+b);
}
```

And why casting `128` to `i8` is `-128`.

```rust runnable
#[allow(overflowing_literals)]
fn main() {
    println!("128 as a i8 is : {}", 128 as i8);
}
```

To understand better about the casting, we need to review about Signed, Ones’ Complement and Two’s Complement.

We will also cover adding a negative number, bitwise negation, and converting a binary to an unsigned and signed decimal.

Let’s start from Rust integer types first.