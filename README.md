#  EXP-04 FULL_ADDER_SUBTRACTOR

Implementation-of-Full-Adder-and-Full-subtractor-circuit

**AIM:**

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

**Equipments Required:**

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

**Full Adder and Full Subtractor**

**Full Adder**

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin 

Carry = AB + ACin + BCin

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/0f30ba51-5ffb-4198-845f-18e054f675e7)

**Figure -1 FULL ADDER**

**Full Subtractor**

A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.

![image](https://github.com/naavaneetha/FULL_ADDER_SUBTRACTOR/assets/154305477/02b24f51-ab51-4304-9ad6-7b81ffc1ead5)

Diff = A ⊕ B ⊕ Bin 

Borrow out = A'Bin + A'B + BBin

**Truthtable**

**Procedure**

Write the detailed procedure here

**Program:**

/* Program to design a half subtractor and full subtractor circuit and verify its truth table in quartus using Verilog programming. 

Developed by: MITHUN S

RegisterNumber: 212224240088
*/
```
module exp04(sum,cout,a,b,cin);
output sum;
output cout;
input a;
input b;
input cin;
wire sl,cl,c2;
xor (sl,a,b);
and (cl,a,b);
xor (sum,sl,cin);
and (c2,sl,cin);
or (cout,c2,cl);
endmodule
```
```
module exp04(df,bo,a,b,bin);
input a,b,bin;
output df,bo;
wire w1,w2,w3;
assign w1=a^b;
assign w2=(~a&b);
assign w3=(~w1&bin);
assign df=w1^bin;
assign bo=w2|w3;
endmodule
```

**RTL Schematic**

![Screenshot 2025-04-27 160554](https://github.com/user-attachments/assets/b89f0c72-cc7c-4940-bfb2-3e990f4ea9ea)

![Screenshot 2025-04-27 162512](https://github.com/user-attachments/assets/072b0c43-c81e-4908-9144-eb2cfbc34313)


**Output Timing Waveform**

![Screenshot 2025-04-27 160529](https://github.com/user-attachments/assets/591f16a2-2bfc-4aee-8fdf-64bc66696190)

![Screenshot 2025-04-27 162457](https://github.com/user-attachments/assets/7666b098-51ac-4b11-8732-204fc6c7be8f)




**Result:**

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.



