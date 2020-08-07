> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Rust signed two’s complement integer types

Now let’s compare negative numbers of signed two’s complement from the above table (from -1 to -7) to Rust’s signed integers.

```rust runnable
fn main() {
    let i1:i32 = -1;
    let i2:i32 = -2;
    let i3:i32 = -3;
    let i4:i32 = -4;
    let i5:i32 = -5;
    let i6:i32 = -6;
    let i7:i32 = -7;
    println!("{} in binary is {:b}", i1, i1);
    println!("{} in binary is {:b}", i2, i2);
    println!("{} in binary is {:b}", i3, i3);
    println!("{} in binary is {:b}", i4, i4);
    println!("{} in binary is {:b}", i5, i5);
    println!("{} in binary is {:b}", i6, i6);
    println!("{} in binary is {:b}", i7, i7);
}
```

They are exactly the same except Rust uses the default 32-bit. Rust’s signed integer types are called **the signed two’s complement integer types**.