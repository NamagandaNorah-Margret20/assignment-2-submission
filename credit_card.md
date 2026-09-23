## Introduction

The C++ program i wrote is for checking whether a credit card number is valid.

I used the Luhn algorithm for the checking. The program also checks the number of digits and some of the starting digits of the card number.

## How it works

The user first enters the card number. I used `long long` instead of `int` because the card number can be quite large and an `int` cannot store that many digits.

Most of the checking is done in the `isValid()` function. First, it uses `getSize()` to find how many digits are in the number. The card number should have between 13 and 16 digits.

It then checks the starting digits using `prefixMatched()`. The starting digits being checked are 4, 5, 37 and 6.

The program then gets two sums using `sumOfDoubleEvenPlace()` and `sumOfOddPlace()`. These are needed for the Luhn algorithm. The two results are added together and if the answer can be divided by 10 without a remainder, the card number is considered valid.

## The functions

For `sumOfDoubleEvenPlace()`, I divide the number by 10 first. This helps me start working from the correct side of the card number. I then take the digit and double it.

I used `getDigit()` because doubling a digit can give a two-digit number. For example, if the digit is 7, doubling it gives 14. Instead of adding 14 as it is, the 1 and 4 are added to get 5.

In `sumOfOddPlace()`, I use `% 10` to get the last digit. After getting that digit, I divide the number by 100. This skips the next digit so that I can get the following one.

`getSize()` uses a `while` loop. Each time the number is divided by 10, one digit is removed, so the loop keeps counting until there are no more digits.

For `getPrefix()`, I also keep dividing the number by 10. I do this until only the number of digits I need for the prefix are left. This is then used by `prefixMatched()` to check the beginning of the card number.

## C++ things I used

- Function declarations and definitions
- Functions with parameters and return values
- `long long` and `int`
- `if` statements
- `while` loops
- Logical operators
- `%` modulus
- Integer division
- `static_cast<int>()`
- `true` and `false`
- `cin` and `cout`


