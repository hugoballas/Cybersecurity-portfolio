##This folder contains my Linux learning notes and practical exercises.

## Data Representation

#### Objective

Learn how computers manage to do all their calculations when they can read and write only two states and interpret them as 0 and 1.

Understand how computers represent and store data using binary, hexadecimal, and character encoding.

examples:
* 0
* 1
* 1010
* 1111111

A group of 8 bits is called a byte

### Decimal to binary

* 1 - 00000001
* 2 - 00000010
* 4 - 00000100
* 8 - 00001000

### Hexadecimal

Hexadecimal is base-16 and uses:

0–9 and A–F

#### examples:
* #3BC81E - green (color)
* #EB0037 - 11101011 00000000 00110111 (binary representation)
* #D4D8DF - 212 216 223 (decimal representation)


### Binary numbers

0000 = 0 × 23 + 0 × 22 + 0 × 21 + 0 × 20 = 0 × 8 + 0 × 4 + 0 × 2 + 0 × 1 = 0

0001 = 0 × 23 + 0 × 22 + 0 × 21 + 1 × 20 = 0 × 8 + 0 × 4 + 0 × 2 + 1 × 1 = 1

0010 = 0 × 23 + 0 × 22 + 1 × 21 + 0 × 20 = 0 × 8 + 0 × 4 + 1 × 2 + 0 × 1 = 2

0011 = 0 × 23 + 0 × 22 + 1 × 21 + 1 × 20 = 0 × 8 + 0 × 4 + 1 × 2 + 1 × 1 = 3


#### exercise:
* 1100 = 1 × 23 + 1 × 22 + 0 × 21 + 0 × 20 = 1 × 8 + 1 × 4 + 0 × 2 + 0 × 1 = 8 + 4 + 0 + 0 = 12
* 1101 = 1 × 23 + 1 × 22 + 0 × 21 + 1 × 20 = 1 × 8 + 1 × 4 + 0 × 2 + 1 × 1 = 8 + 4 + 0 + 1 = 13

* 1110 = 1 × 23 + 1 × 22 + 1 × 21 + 0 × 20 = 1 × 8 + 1 × 4 + 1 × 2 + 0 × 1 = 8 + 4 + 2 + 0 = 14

* 1111 = 1 × 23 + 1 × 22 + 1 × 21 + 1 × 20 = 1 × 8 + 1 × 4 + 1 × 2 + 1 × 1 = 8 + 4 + 2 + 1 = 15


#### example (hexadecimal to decimal)
* 9BDF = 9 × 163 + 11 × 162 + 13 × 161 + 15 × 160 = 9 × 4096 + 11 × 256 + 13 × 16 + 15 × 1 = 39,903


#### example (octal to decimal)
* 357 = 3 × 82 + 5 × 81 + 7 × 80 = 3 × 64 + 5 × 8 + 7 × 1 = 239



