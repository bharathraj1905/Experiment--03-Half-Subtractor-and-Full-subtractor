# Experiment--03-Half-Subtractor-and-Full-subtractor
## Implementation-of-Half-subtractor-and-Full-subtractor-circuit
## AIM:
To design a half subtractor and full subtractor circuit and verify its truth table in Quartus using Verilog programming.

## Equipments Required:
## Hardware – PCs, Cyclone II , USB flasher
## Software – Quartus prime
## Theory
Subtractor circuits take two binary numbers as input and subtract one binary number input from the other binary number input. Similar to adders, it gives out two outputs, difference and borrow (carry-in the case of Adder). There are two types of subtractors.

## Half Subtractor Full Subtractor
## Half Subtractor
The half-subtractor is a combinational circuit which is used to perform subtraction of two bits. It has two inputs, X (minuend) and Y (subtrahend) and two outputs D (difference) and B (borrow). To perform x - y, we have to check the relative magnitudes of x and y. If x ;;, y, we have three possibilities: 0 - 0 = 0, 1 - 0 = 1, and 1 - I = 0. The result is called the difference bit. If x < y, we have 0 - I, and it is necessary to borrow a 1 from the next higher stage. The I borrowed from the next higher stage adds 2 to the minuend bit, just as in the decimal system a borrow adds 10 to a minuend digit. With the minuend equal to 2, the difference becomes 2 - I = 1. The half-subtractor needs two outputs. One output generates the difference and will be designated by the symbol D. The second output, designated B for borrow, generates the binary signal that informs the next stage that a I has been borrowed.
![half-subtractor9](https://user-images.githubusercontent.com/36288975/166112538-58c3bc7c-ee5d-4e6a-ac8d-8e8328efe27a.png)


Sum = X'Y+XY' = X ⊕ Y
Carry=X'Y

## Full Subtractor
A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow. 
![full-subtractor6](https://user-images.githubusercontent.com/36288975/166112541-24c68359-3de8-4674-ae22-8272ffc385ed.png)


Diff = A ⊕ B ⊕ Bin B = A'Bin + A'B + BBin

## Procedure
It can be implemented using two half subtractors and one OR gate as: Giving one half subtractor the inputs A and B that gives outputs Diff1 and B1. Giving second half subtractor inputs Bin and Diff1 from first subtractor that gives outputs B2 and D (difference for the full subtractor).

## Program:
Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming.
Developed by: b.barathraj
RegisterNumber: 212222230019

```
module half_sub(x, y, d, b, x1);
input x,y;
output x1, d, b;
xor(d, x, y);
not(x1, x);
and(b, x1, y);
endmodule

```
```
module full_sub(x, y, z, d, b, x1, x2, x3, x4, x5);
input x,y,z;
output d, b, x1, x2, x3, x4 ,x5;
xor(x1, x, y);
xor(d, x1, z);
not(x2, x);
and(x3, x2, y);
and(x4, x3, z);
and(x5, y, z);
or(b, x3, x4, x5);
endmodule

```
## Output:
## Truthtable
![truth table 4 1](https://user-images.githubusercontent.com/121490575/233253354-28fccc40-7702-487a-a894-4e9e99d3c44e.png)

![truth table 4 2](https://user-images.githubusercontent.com/121490575/233253518-943b524b-e75f-448b-a6a1-72ec902d6c02.png)


##  RTL realization
![rtl exp 4 1](https://user-images.githubusercontent.com/121490575/233253613-9680a583-5b09-45bd-84e6-b3bf56a63276.png)

![rtl exp 4 2](https://user-images.githubusercontent.com/121490575/233253711-19cb22e2-b075-41d3-97c9-297642f1a5ca.png)

## Timing diagram 

![timing exp 4 1](https://user-images.githubusercontent.com/121490575/233253761-ec3b2f2e-d68d-4cbc-b156-edf95fb7ba51.png)

![timing exp 4 2](https://user-images.githubusercontent.com/121490575/233253822-1f214f07-aef1-4ead-a3d5-c6a2fc87ee8a.png)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
