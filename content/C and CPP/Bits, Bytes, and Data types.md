---
title: Bits, Bytes, and their behaviour
draft: "false"
description: Introduction to bits, bytes, and their functioning.
tags:
  - c
  - cpp
  - bits
  - bytes
---
## Intro

1 byte has 8 bits. A single bit can have two states, i.e 0 and 1.  A byte can have 256 unique combination of 0s and 1s. 4 bits is called a nibble. 2 nibble = 1 byte

> To get no. of unique combination with X bits, do this: 2**X

## Primer to `int` datatype

An `int` type variable takes 4 bytes of space which means 32 bits. No. of states that can be created from 32 bits can be calculated like this.

```
Possible states from 32 bits = Math.pow(2, 32)
                             = 4294967296 states
```

So, 4294967296 different numbers can be represented.
## Signed and Unsigned data types

A signed data type allows the negative value to be stored, whereas, unsigned does not allow that.

 For instance, the following is a signed integer. It can hold negative values.
 
```cpp
 int a = -69;
 printf("%d", a);
```

On the other hand, an unsigned integer can hold only positive numbers.

```cpp
unsigned int b = 30;
printf("%u", b);
```

> `%u` is the format specifier for unsigned int.

In signed integers, the first bit (MSB) represents whether the number is positive or negative. In unsigned integers, the first bit is also used to represent the magnitude.
##### Binary Representation

The binary representation of a negative number is done by taking the 2's complement of the positive number.

For instance, here's how we find binary representation of -5 store in `int`.

```
We know,
	binary(int 5) = 00000000 00000000 00000000 00000101

binary(int -5) = 2's complement of binary(5)
           = 1's complement of binary(5) + add 1
           = 1's complement of 00000000 00000000 00000000 00000101 + 1
           = 11111111 11111111 11111111 1111101 + 1
           = 11111111 11111111 11111111 1111110
```

### Ranges of signed and unsigned datatype

Regardless of the signed and unsigned keyword, the number of unique states which could be represented by the datatype remains the same. What changes is the range of numbers it represents.

For instance, the signed integer ranges from -2,147,483,648 to 2,147,483,647. Note that one state is used to represent `0` due to which both it ranges -2,147,483,648 to 2,147,483,647 and not -2,147,483,648 to 2,147,483,648.

The general formula to get the range of numbers a signed data type can represent is as following:

```
x = number of bits in the data type
range = -(Math.pow(2, x) / 2) to (Math.pow(2, x) / 2) - 1
```

As for the unsigned integer, this range becomes 0 to 4294967295 and the formula for it as follows:

```
x = number of bits in the data type
range = 0 to Math.pow(2, x) - 1
```

## Overflows -  What if I assign a bigger number?
