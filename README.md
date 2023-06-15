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
```
Developed by: b.barathraj
RegisterNumber: 212222230019
```
### HALF_SUBTRACTOR :
```
module Halfsub(A,B,Diff,Borrow);
input A,B;
output Diff,Borrow;
wire x;
xor (Diff, A,B);
not(x,A);
and(Borrow,x,B);
endmodule
```
### FULL_SUBTRACTOR :
```
module FulLsub(A,B,C,Diff,Borrow);
input A,B,C;
output Diff,Borrow;
wire p;
assign Diff = ((A^B)^C);
not(p,A);
assign Borrow = ((p&B)|(p&C)|(B&C));
endmodule
```
## Output:
## Truthtable
### HALF_SUBTRACTOR :

![truth table exp 3 1](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/5ef2dfe3-562c-4b33-8425-c5e1586ba0a5)


### FULL_SUBTRACTOR :
![truth table ex 4 2](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/1f23f4f4-3d2d-4541-83fb-7ae1f7608f44)


### RTL realization
### HALF_SUBTRACTOR
![rtl ex 4 1](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/7e3590b2-faf9-4283-ab44-c16ad0e32196)
 :

### FULL_SUBTRACTOR :
![rtl ex 4 2](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/f4b84447-90a4-4f20-88f4-8195cedf373f)


## Timing diagram 
### HALF_SUBTRACTOR :
![time diagram ex 4 1](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/3ce21cb8-7b87-4316-92d5-80433f574f11)


### FULL_SUBTRACTOR :
![time diAGRAM ex 4 2](https://github.com/bharathraj1905/Experiment--03-Half-Subtractor-and-Full-subtractor/assets/121490575/2a0ff24e-d346-4938-942d-df907b8b43b5)


## Result:
Thus the half subtractor and full subtractor circuits are designed and the truth tables is verified using quartus software.
