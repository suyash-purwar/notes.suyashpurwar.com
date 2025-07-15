---
title: Basics of char
draft: "false"
description: Char datatype in C/C++
tags:
  - cpp
  - c
  - char
---
## Intro

A variable of char type is of 1 byte and is always defined by enclosing the value in single quotation marks. The datatype char is actually an integer type only. It is a subset of integer type and behaves like an integer in many ways. It ranges from -127 to 128.

*C states: A char, a short int, an int, a long int, and a long long int are all considered integer types.*

Declaration of char:
```c
char ch = 'X';
```
##### Aside

The first bit represents whether the number is positive or negative. First and last bit are also known as Most Significant and Least Significant bit respectively. Abbreviated as MSB and LSB.

For example:
```
78 --> 01001110

-78 --> 2's complement of (01001110)
	--> (1's complement of) + 1
	--> (Flip all bits) + 1
	--> 10110001 + 1
-78 --> 10110010
```
