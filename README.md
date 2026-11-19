# Dart OOP Assignment: Kigali Bus Card

**Name:** Miada Abdelmonim Hassan Obeid
**Student ID:** 26308/2024

## My numbers
- D = 8, L = 08
- Starting balance = 1080 RWF
- Bus fare = 208 RWF
- Student discount = 18%


## Part 1: There is no setter for balance . Why is that a good idea for a bus card?
If balance had a setter, anyone could write card.balance = 1000000 and give themselves free money. Without a setter, the balance can only change through topUp and pay, and those two methods check the rules first (top-up must be 500 to 50000 RWF, and you cannot pay more than the balance). This keeps the money safe.

## Part 2: What does ~/ do? Try print(237 * 17 / 100); andprint(237 * 17 ~/ 100); and explain the difference?
/ gives a normal division with decimals, and ~/ gives integer division: it throws away the decimal part.
print(237 * 17 / 100); prints 40.29
print(237 * 17 ~/ 100); prints 40
The difference is that ~/ removes the decimal part, so I get a whole number. This is useful for the discount because money here is counted in whole RWF.

## Part 3: Output of main.dart
Error: name too short
Owner: Miada | Balance: 1080 RWF
Owner: Miada Abdelmonim Hassan Obid | Balance: 1080 RWF
Error: top-up must be 500 to 50000 RWF
Topped up 2000 RWF
Paid 208 RWF
Paid 208 RWF
Owner: Miada Abdelmonim Hassan Obid | Balance: 2664 RWF
Student discount: 37 RWF
Paid 171 RWF
Owner: Miada Abdelmonim Hassan Obid | Balance: 909 RWF
Student card: 18% off

## Part 4: Bug table
| Bug | The line | Why it is wrong (your words) | Your fix |
|-----|----------|------------------------------|----------|
| 1 | String _brand; and int _battery; | Dart does not allow a field without a starting value. | String _brand = ''; and int _battery = 0; |
| 2 | SmartPhone(String brand, int battery, String system) { | The child constructor does not build the parent Phone first, so brand and battery are missing. | Add : super(brand, battery) |
| 3 | @override void restart() { | @override only works if the parent has that method, and Phone has no restart. | Remove @override |
| 4 | p.battery = 100; | Phone has a getter but no setter, so the battery cannot be changed. | Add set battery(int value) that accepts only 0 to 100 |
| 5 | print(p.battery()); | battery is a getter, not a method, so it must not have (). | print(p.battery); |
| Not a bug | Phone p = new Phone('Tecno', 50); | new is optional in Dart but still allowed, so the line works. | (none) |

## Part 5 :My prediction:
It prints 1 and then 5.
For Bag a: add() makes items 1, then a.items = -5 is refused by the setter because it only accepts values 0 or more, so it prints 1.
For BigBag b: each add() calls super.add() twice, so it adds 2 each time. Two calls make 4. Then b.items = b.items + 1 makes it 5, so it prints 5.
Real output:
1
5
Was I right?
Yes, I was right.