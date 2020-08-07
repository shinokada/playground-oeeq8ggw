> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Signed Integer Types

The **default** integer type in Rust is `i32`. Signed integer types in Rust start with `i` and it has 8, 16, 32, 64, and 128-bit. 

The minimum and maximum values are from **-(2ⁿ⁻¹) to 2ⁿ⁻¹-1**. The `-1` in the `n-1` is the sign bit (positive or negative), which we cover in the next section.

For example `i8` has -(2⁷) to 2⁷-1, which is -128 to 127. The following table shows all the details for signed integers.

| DATA TYPE | MIN                         | MAX                        | Length  |
| --------- | --------------------------- | -------------------------- | ------- |
| i8        | -128                        | 127                        | 8-bit   |
| i16       | -32768                      | 32767                      | 16-bit  |
| i32       | -2147483648                 | 2147483647                 | 32-bit  |
| i64       | -92233720368547...          | 92233720368547...          | 64-bit  |
| i128      | -17014118346046923173168... | 17014118346046923173168... | 128-bit |

```rust runnable
fn main() {
    println!(" i8 has the min value of {}.", i8::min_value());
    println!(" i8 has the max value of {}.", i8::max_value());
    println!(" i16 has the min value of {}.", i16::min_value());
    println!(" i16 has the max value of {}.", i16::max_value());
    println!(" i32 has the min value of {}.", i32::min_value());
    println!(" i32 has the max value of {}.", i32::max_value());
    println!(" i64 has the min value of {}.", i64::min_value());
    println!(" i64 has the max value of {}.", i64::max_value());
    println!(" i128 has the min value of {}.", i128::min_value());
    println!(" i128 has the max value of {}.", i128::max_value());
}
```