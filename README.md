Implementation-of-Full-Adder-and-Full-subtractor-circuit

AIM:

To design a Full Adder and Full Subtractor circuit and verify its truth table in Quartus using Verilog programming.

Equipments Required:

Hardware – PCs, Cyclone II , USB flasher

Software – Quartus prime

Full Adder and Full Subtractor

Full Adder

Full adder is a digital circuit used to calculate the sum of three binary bits. It consists of three inputs and two outputs. Two of the input variables, denoted by A and B, represent the two significant bits to be added. The third input, Cin, represents the carry from the previous lower significant position. Two outputs are necessary because the arithmetic sum of three binary digits ranges in value from 0 to 3, and binary 2 or 3 needs two digits. The two outputs are sum and carry.

Sum =A’B’Cin + A’BCin’ + ABCin + AB’Cin’ = A ⊕ B ⊕ Cin

Carry = AB + ACin + BCin

Figure -1 FULL ADDER
<img width="531" height="274" alt="image" src="https://github.com/user-attachments/assets/04fffb50-5dfe-405a-a99d-a0bdd82d201e" />

Full Subtractor
<img width="657" height="286" alt="image" src="https://github.com/user-attachments/assets/076ae121-923d-4271-890e-b3cfe4035ab0" />


A full subtractor is a combinational circuit that performs subtraction involving three bits, namely minuend, subtrahend, and borrow-in . It accepts three inputs: minuend, subtrahend and a borrow bit and it produces two outputs: difference and borrow.
Diff = A ⊕ B ⊕ Bin

Borrow out = A'Bin + A'B + BBin

Truthtable

FULL ADDER:
<img width="701" height="417" alt="image" src="https://github.com/user-attachments/assets/2354ddf8-ed42-412a-8b1d-1d3a29184599" />

FULL SUBTRACTOR:
<img width="716" height="433" alt="image" src="https://github.com/user-attachments/assets/35d15bf8-f538-4622-a411-12bd1e942bdd" />



Procedure

Type the program in Quartus software
Compile and run the program
Generate the RTL schematic and save the logic diagram
Create nodes for inputs and outputs to generate the timing diagram
For different inputs combinations generate the timing diagram
Program:

FULL ADDER:

module fa(a,b,cin,sum,carry); input a,b,cin; output sum,carry; assign sum=( (a ^ b)^cin); assign carry= ( (a & b)| ( cin &(a ^ b ))); endmodule

FULL SUBTRACTOR:
```
module full_adder (
    input  wire a, b, cin,   // Inputs
    output wire sum, carry   // Outputs
);

    // Logic equations
    assign sum   = a ^ b ^ cin;                  // XOR for sum
    assign carry = (a & b) | (b & cin) | (a & cin); // Majority function for carry

endmodule

module full_subtractor (
    input  wire a, b, bin,       // Inputs
    output wire diff, borrow     // Outputs
);

    // Logic equations
    assign diff   = a ^ b ^ bin;                  // Difference
    assign borrow = (~a & b) | (~(a ^ b) & bin);  // Borrow logic

endmodule

```
Developed by:KAVIRAJ.P
Register Number:25017431

RTL Schematic

FULL ADDER:
[exp4 RTL.pdf](https://github.com/user-attachments/files/24106847/exp4.RTL.pdf)




FULL SUBTRACTOR:
[exp4 RTL.pdf](https://github.com/user-attachments/files/24106797/exp4.RTL.pdf)


Output Timing Waveform

FULL ADDER:
[wave img.bmp](https://github.com/user-attachments/files/24106800/wave.img.bmp)


FULL SUBTRACTOR:
[wave img.bmp](https://github.com/user-attachments/files/24106819/wave.img.bmp)


Result:

Thus the Full Adder and Full Subtractor circuits are designed and the truth tables is verified using Quartus software.
