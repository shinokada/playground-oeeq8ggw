> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)


# Casting in Rust

[**Casting**](https://doc.rust-lang.org/rust-by-example/types/cast.html) means changing the data type of a piece of data from one type to another.

`as`[ keyword](https://doc.rust-lang.org/std/keyword.as.html) turns primitive types into other primitive types. We can use `as` keyword to solve the code in the introduction.

```rust runnable
fn main() {
    let a: i16 = 2;
    let b: u16 = 4;
    println!("{}", a+b as i16);
}
```

When you cast from a small length to a larger length, for example from 8-bit to 16-bit, there won’t be any problem but when you cast down, you may have a problem.