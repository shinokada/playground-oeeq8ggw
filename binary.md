> This story was originally published on [Medium](https://towardsdatascience.com/unsinged-signed-integers-and-casting-in-rust-9a847bfc398f)

Follow me:
- [@shinokada](https://twitter.com/shinokada)
- [Medium](https://medium.com/@shinichiokada)

# 4-bit Signed Binary Number Comparison

The following table shows the comparison of three signed number representations.

| Decimal | Signed Magnitude | Signed Ones' Complement | Signed Two's Complement |
| :-----: | :--------------: | :---------------------: | :---------------------: |
|   +7    |       0111       |          0111           |          0111           |
|   +6    |       0110       |          0110           |          0110           |
|   +5    |       0101       |          0101           |          0101           |
|   +4    |       0100       |          0100           |          0100           |
|   +3    |       0011       |          0011           |          0011           |
|   +2    |       0010       |          0010           |          0010           |
|   +1    |       0001       |          0001           |          0001           |
|   +0    |       0000       |          0000           |          0000           |
|   -0    |       1000       |          1111           |            -            |
|   -1    |       1001       |          1110           |          1111           |
|   -2    |       1010       |          1101           |          1110           |
|   -3    |       1011       |          1100           |          1101           |
|   -4    |       1100       |          1011           |          1100           |
|   -5    |       1101       |          1010           |          1011           |
|   -6    |       1110       |          1001           |          1010           |
|   -7    |       1111       |          1000           |          1001           |

