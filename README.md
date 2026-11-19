# Dart OOP Assignment: Kigali Bus Card

**Name:** Miada Abdelmonim Hassan Obeid
**Student ID:** 26308/2024

## My numbers
- D = 8, L = 08
- Starting balance = 1080 RWF
- Bus fare = 208 RWF
- Student discount = 18%

## Output of main.dart
(paste here)

## Part 1: There is no setter for balance . Why is that a good idea for a bus card?
If balance had a setter, anyone could write card.balance = 1000000 and give themselves free money. Without a setter, the balance can only change through topUp and pay, and those two methods check the rules first (top-up must be 500 to 50000 RWF, and you cannot pay more than the balance). This keeps the money safe.

## Part 2: What does ~/ do? Try print(237 * 17 / 100); andprint(237 * 17 ~/ 100); and explain the difference?
/ gives a normal division with decimals, and ~/ gives integer division: it throws away the decimal part.
print(237 * 17 / 100); prints 40.29
print(237 * 17 ~/ 100); prints 40
The difference is that ~/ removes the decimal part, so I get a whole number. This is useful for the discount because money here is counted in whole RWF.

