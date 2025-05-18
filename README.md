# BOOLEAN_FUNCTION_MINIMIZATION

**AIM:**

To implement the given logic function verify its operation in Quartus using Verilog programming.

F1= A’B’C’D’+AC’D’+B’CD’+A’BCD+BC’D 

F2=xy’z+x’y’z+w’xy+wx’y+wxy

**Equipment Required:**

Hardware – PCs, Cyclone II , USB flasher

**Software – Quartus prime**

**Theory**
Boolean Function Minimization is the process of reducing a Boolean expression to its simplest form without changing its functionality. This minimization reduces the number of gates and inputs required, optimizing circuit design.

**Logic Diagram**
Fundamental building blocks like AND, OR, and NOT gates are used to implement Boolean expressions. Karnaugh Map (K-map): A graphical technique for minimizing Boolean expressions by grouping terms based on commonalities. The given Boolean functions can be minimized as follows:

F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D The terms can be simplified using K-map techniques to reduce the complexity of the circuit. F2 = xy’z + x’y’z + w’xy + wx’y + wxy Similar simplification can be done for this function to reduce the gate count. The resulting minimized expressions are implemented using Verilog HDL and simulated on the Quartus Prime tool. The outputs can then be verified on an FPGA board (e.g., Cyclone II).

**Truth Table**
F1 = A’B’C’D’ + AC’D’ + B’CD’ + A’BCD + BC’D:
![434143665-41442d0d-d869-4ffb-9792-700ac09bd520](https://github.com/user-attachments/assets/7ce981f3-0ee8-4ba9-9492-d6b0c223eb13)

F2 = xy’z + x’y’z + w’xy + wx’y + wxy:
![434143632-50838a15-f544-4630-9301-96d0fdca767d](https://github.com/user-attachments/assets/b1f68b32-642f-4726-8750-eeec408bd260)



**Procedure**

1.	Type the program in Quartus software.

2.	Compile and run the program.

3.	Generate the RTL schematic and save the logic diagram.

4.	Create nodes for inputs and outputs to generate the timing diagram.

5.	For different input combinations generate the timing diagram.


**Program:**

/* Program to implement the given logic function and to verify its operations in quartus using Verilog programming. 
Developed by: PARTHASARATHI S
RegisterNumber: 212223040144
*/
module (a,b,c,d,w,x,y,z,f1,f2);
  input a,b,c,d,w,x,y,z;
  output f1,f2;
  wire x1,x2,x3,x4,x5,y1,y2,y3,y4,y5;
  assign x1=((~a)&(~b)&(~c)&(~d));
  assign x2=(a&(~c)&(~d));
  assign x3=((~b)&(c)&(~d));
  assign x4=((~a)&(b)&(c)&(d));
  assign x5=(b&(~c)&(d));
  assign f1=x1|x2|x3|x4|x5;
  
  assign y1=(x&(~y)&(z));
  assign y2=((~x)&(~y)&z);
  assign y3=((~w)&x&y);
  assign y4=(w&(~x)&(y));
  assign y5=(w&x&y);
  assign f2=y1|y2|y3|y4|y5;
  endmodule 


**RTL realization**
![434142940-c169332a-8a88-4787-abf6-2fab98cbdf2b](https://github.com/user-attachments/assets/f69b1602-34f4-4491-824e-a98824ea1fe1)

**Timing Diagram**
![440133102-2022a63a-22c4-4d06-a1a1-15e7bf9f0272](https://github.com/user-attachments/assets/948cf991-8f8b-4def-85f9-b8475fce85fc)

**Result:**

Thus the given logic functions are implemented using and their operations are verified using Verilog programming.

