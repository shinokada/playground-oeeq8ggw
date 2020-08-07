> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Casting to an Unsigned Type

## Method 1

When you cast to an unsigned type, T, T::MAX + 1 is added or subtracted until the value fits into the new type.

Example 1: Casting 1000 from the default, `i32` to `u8`

`u8` has the max number of 255, so we subtract 255+1, which is 256 from 1000 until it gets less than 255.

```
1000 - 256             = 744 
1000 - 256 - 256       = 488 
1000 - 256 - 256 - 256 = 232
```

```rust runnable
#[allow(overflowing_literals)]
fn main() {
    println!("1000 as a u8 is : {}", 1000 as u8);
}
```

## Method 2

1000₁₀ in decimal is 11 1110 1000₂ in binary. We can take the last 8 bits, which is `1110 1000` and it is 232 in decimal.

An interesting number is 256₁₀.

```rust runnable
#[allow(overflowing_literals)]
fn main() {
    println!("256 as a u8 is : {}", 256 as u8);
}
```

256<sub>10</sub> is 100000000<sub>2</sub> in binary. If you take the last 8 bits it is `00000000`.