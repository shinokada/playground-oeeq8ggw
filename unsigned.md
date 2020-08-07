> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Unsigned Integer Types

Unsigned integer types in Rust start with `u` and it has 8, 16, 32, 64, and 128-bit. The minimum and maximum values are from **0 to 2ⁿ-1**.

For example `u8` has 0 to 2⁸-1, which is 255. The following table shows all the details for unsigned integers.

| DATA TYPE | MIN  | MAX                                     | Length  |
| :-------- | :--- | :-------------------------------------- | ------- |
| u8        | 0    | 255                                     | 8-bit   |
| u16       | 0    | 65535                                   | 16-bit  |
| u32       | 0    | 4294967295                              | 32-bit  |
| u64       | 0    | 18446744073709551615                    | 64-bit  |
| u128      | 0    | 340282366920938463463374607431768211455 | 128-bit |


```rust runnable
fn main() {
    println!(" u8 has the max value of {}.", u8::max_value());
    println!(" u16 has the max value of {}.", u16::max_value());
    println!(" u32 has the max value of {}.", u32::max_value());
    println!(" u64 has the max value of {}.", u64::max_value());
    println!(" u128 has the max value of {}.", u128::max_value());
}
```

If you try to assign a negative number to an unsigned type, it will fail.

```rust runnable
fn main() {
    let u:u32 = -1;
    println!("{} in binary is {:b}", u, u);
}

// error[E0600]: cannot apply unary operator `-` to type `u32`
//  --> main.rs" data-line="2" data-column="17">main.rs:2:17
//   |
// 2 |     let u:u32 = -1;
//   |                 ^^ cannot apply unary operator `-`
//   |
//   = note: unsigned values cannot be negated
```

`-` is one of Rust's [**unary** **operators**](https://doc.rust-lang.org/reference/expressions/operator-expr.html) and it is the negation operator for signed integer types and floating-point types.