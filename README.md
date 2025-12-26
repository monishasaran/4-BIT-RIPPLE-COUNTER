# 4-BIT-RIPPLE-COUNTER

**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**
1.	Type the program in Quartus software.
2.	Compile and run the program.
3.	Generate the RTL schematic and save the logic diagram.
4.	Create nodes for inputs and outputs to generate the timing diagram.
5.	For different input combinations generate the timing diagram.



**PROGRAM**
module EXPR6(q, clk, reset); 
output [3:0] q;
input clk, reset;
T_FF tffo(q[0], clk, reset); 
T_FF tff1(q[1], q[0], reset); 
T_FF tff2(q[2], q[1], reset); 
T_FF tff3(q[3], q[2], reset); 
endmodule

module D_FF(q, d, clk, reset); 
output q;
input d, clk, reset;
reg q;
always @(posedge reset or negedge clk)
 if (reset)
q = 1'b0;
 else
q = d;
endmodule

module T_FF(q, clk, reset);
output q;
input clk, reset;
wire d;
D_FF dff0(q, d, clk, reset);
not n1(d, q); // not is Verilog-provided primitive. 
endmodule




 Developed by:Monisha.S RegisterNumber:25017984


**RTL LOGIC FOR 4 Bit Ripple Counter**
<img width="1167" height="447" alt="Screenshot 2025-12-19 120211" src="https://github.com/user-attachments/assets/595fab4a-27d0-423c-9583-238203d9e42e" />


**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
<img width="1646" height="438" alt="Screenshot 2025-12-19 120437" src="https://github.com/user-attachments/assets/578dec2c-7cd9-4dfb-8d6a-311c23145400" />


**RESULTS**

Thus the 4 Bit Ripple Counter using verilog and validating their functionality using their functional tables is verified.
