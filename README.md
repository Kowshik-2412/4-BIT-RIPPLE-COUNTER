# 4 BIT RIPPLE CARRY ADDER
# Developed by: Kowshik P
# RegisterNumber: 212224040164
**AIM:**

To implement  4 Bit Ripple Ripple Carry Adder using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A 4-bit Ripple Carry Adder consists of four full adders connected in series. Each full adder takes in two input bits (one from each operand) and a carry-in bit, and produces a sum bit and a carry-out bit. The carry-out from each full adder is rippled to the carry-in of the next higher-order adder, hence the name "ripple carry".

The first full adder (least significant bit) receives the least significant bits of the operands and an initial carry-in (Cin = 0). The carry-out of this adder is passed to the next full adder, which adds the next pair of bits along with the incoming carry. This process continues through all four full adders.

Since the carry must propagate through each adder sequentially, the delay in getting the final result increases with the number of bits. This is called propagation delay, and it is a key limitation of the ripple carry adder.

![image](https://github.com/user-attachments/assets/685916c8-ad52-4c5a-99a4-7b0ec1d97772)

Timing Explanation:
In the timing diagram,

S0 (the least significant sum bit) is generated immediately after inputs A0, B0, and Cin are applied.

S1 depends on the carry-out from the first adder, so it appears after a delay.

S2 appears after the second carry has propagated, and so on.

The final carry-out (Cout) appears last, after all carry bits have rippled through the adders.

![image](https://github.com/user-attachments/assets/cff35a44-e0a5-455c-b2ca-353494c6de25)


![image](https://github.com/user-attachments/assets/d7d0f628-8d42-4b2c-ac90-230c3ef40641)


This sequential carry propagation is what characterizes the ripple carry adder and distinguishes it from faster designs like carry look-ahead adders.

**Procedure**

1.Provide two 4-bit binary numbers (A and B) as inputs to the adder.

Set the initial carry-in (Cin) to 0 for the least significant bit adder.

3.Instantiate the RippleCarryAdder module, which consists of four connected full adders.

4.Perform bit-wise addition for each corresponding bit of A and B, along with the carry from the previous stage.

5.Propagate the carry from each full adder to the next higher-order adder (LSB to MSB).

6.Obtain the 4-bit sum output and the final carry-out after the last full adder.

7.Conduct functional testing by displaying the inputs (A, B), intermediate carries, sum, and final carry-out for all combinations of A and B (from 0000 to 1111).


**PROGRAM**
```
module full_adder (input a, b, cin, output sum, cout);
 assign sum = a^b^cin;
 assign cout = (a & b) | (b & cin) | (a & cin);
endmodule
module fd (input [3:0] A, B, input Cin, output [3:0] Sum, output Cout);
 wire c1, c2, c3;
 full adder FAO (A[0], B[0], Cin, Sum[0], C1);
 full_adder FA1 (A[1], B[1], cl, Cin, Sum[0], C2);
 full_adder FA2 (A[2], B[2], c2, Cin, Sum[0], C3);
 full_adder FA3 (A[3], B[3], c3, Cin, Sum[0], Cout);
endmodule
```



**RTL LOGIC FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/f0f7e30c-1dad-40dc-9e98-7b80b9eb99e8)



**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![image](https://github.com/user-attachments/assets/ca303433-0aba-4fb4-97e4-8ec47baa0e24)



**RESULTS**
Thus the program to implement a 4 Bit Ripple Carry Adder using verilog and validating their functionality using their functional tables is successfully completed.
