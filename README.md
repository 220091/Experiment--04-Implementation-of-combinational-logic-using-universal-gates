 AIM:
To implement the given logic function using NAND and NOR gates and to verify its operation in Quartus using Verilog programming.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')' using NAND gate
F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')' using NOR gate
Equipments Required:
 Hardware – PCs, Cyclone II , USB flasher
 Software – Quartus prime


 Theory
Logic gates are electronic circuits which perform logical functions on one or more inputs to produce one output. 

 Using NAND gates
NAND gate is actually a combination of two logic gates i.e. AND gate followed by NOT gate. So its output is complement of the output of an AND gate.This gate can have minimum two inputs, output is always one. By using only NAND gates, we can realize all logic functions: AND, OR, NOT, X-OR, X-NOR, NOR. So this gate is also called as universal gate. First note that the entire expression is inverted and we have three terms ANDed. This means that we must use a 3-input NAND gate. Each of the three terms is, itself, a NAND expression. Finally, negated single terms can be generates with a 2-input NAND gate acting as an inverted.

F=((C'.B.A)'(D'.C.A)'(C.B'.A)')'

 Logic Diagram

Using NOR gates
NOR gate is actually a combination of two logic gates: OR gate followed by NOT gate. So its output is complement of the output of an OR gate. This gate can have minimum two inputs, output is always one. By using only NOR gates, we can realize all logic functions: AND, OR, NOT, Ex-OR, Ex-NOR, NAND. So this gate is also called universal gate. Designing a circuit with NOR gates only uses the same basic techniques as designing a circuit with NAND gates; that is, the application of deMorgan’s theorem. The only difference between NOR gate design and NAND gate design is that the former must eliminate product terms and the later must eliminate sum terms.

F=(((C.B'.A)+(D.C'.A)+(C.B'.A))')'

 
 Procedure
 
 Program:

Program to implement the given logic function using NAND and NOR gates and to verify its operations in quartus using Verilog programming.

PROGRAM 1:

module expfour(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3;

assign f1 = (~c&~b&~a);

assign f2 = (~d&~c&~a);

assign f3 = (c&~(~b)&~a);

assign f= f1&~f2&~f3;

endmodule


PROGRAM 2:

module expfourtwo(a,b,c,d,f);

input a,b,c,d;

output f;

wire f1,f2,f3,f4;

assign f1 = c&(~b)&a;

assign f2 = d&(~c)&a;

assign f3 = c&(~b)&a;

assign f4 = ~(f1|f2|f3);

not(f,f4);

endmodule





Developed by: JENIFER.A

RegisterNumber: 22009141 

 RTL realization

Output:

RTL

PROGRAM 1

![PRO1](https://user-images.githubusercontent.com/121572543/211182000-1a4890d2-5db3-4137-81b6-d484460e4bea.png)


PROGRAM 2


![PRO2](https://user-images.githubusercontent.com/121572543/211182009-2b4722c4-3ab3-455f-9370-b0f65b32afa4.png)


 Timing Diagram
 
 PROGRAM 1
 
 ![PRO TIME 1](https://user-images.githubusercontent.com/121572543/211182039-17a61fb7-a738-4fba-967f-6a1b28b12535.png)

 
 PROGRAM 2
 
 ![PRO TIME 2](https://user-images.githubusercontent.com/121572543/211182050-501b9d38-85af-4a9f-90f5-244ffdbc07c9.png)

OUTPUT


TRUTH TABLE


PROGRAM 1

![PRO TRU1](https://user-images.githubusercontent.com/121572543/211182066-2c94e298-6505-4e65-bca3-637c52f785e5.png)


PROGRAM 2

![PRO TRU2](https://user-images.githubusercontent.com/121572543/211182071-253dba70-4641-4a5c-b6c4-4269566e583a.png)

 
 Result:
Thus the given logic functions are implemented using NAND and NOR gates and their operations are verified using Verilog programming.
