> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# Bitwise Negation

Rust uses `!` for the Bitwise Negation (Bitwise NOT). This produces different results depends on the type.

```rust runnable
fn main() {
    let i:i32;
    let u:u32;
    i = 2;
    u = 2;
    println!("u is {}", u);
    println!("u in binary is {:b}", u);
    println!("i is {}", i);
    println!("i in binary is {:b}", i);
    println!("Bitwise negation !u is {}", !u);
    println!("Bitwise negation !i is {}", !i);
}
```

As you see `!2` with the unsigned type returns `4294967293` and with the signed type returns `-3`.

The bitwise negation on a signed integer returns the two’s complement as we saw previously in [Rust signed two’s complement integer types](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f#0a26).


# Adding a Negative Number

The subtraction is the same as adding a negative number.

```
5 - 2 = 5 + (-2) = 3
```

This applies to binary as well.

```
0101 - 0010 
= 0101 + (-0010) // (1)
= 0101 + 1110    // (2)
= 0011           // this is 3 in decimal number.
```

We find `-0010` by finding the two’s complement of `0010` that is `1110`.
