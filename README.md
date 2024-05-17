AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using vivado 2023.1.

APPARATUS REQUIRED: Vivado 2023.1

PROCEDURE:

Open Vivado: Launch Xilinx Vivado software on your computer.

Create a New Project: Click on "Create Project" from the welcome page or navigate through "File" > "Project" > "New".

Project Settings: Follow the prompts to set up your project. Specify the project name, location, and select RTL project type.

Add Design Files: Add your Verilog design files to the project. You can do this by right-clicking on "Design Sources" in the Sources window, then selecting "Add Sources". Choose your Verilog files from the file browser.

Specify Simulation Settings: Go to "Simulation" > "Simulation Settings". Choose your simulation language (Verilog in this case) and simulation tool (Vivado Simulator).

Run Simulation: Go to "Flow" > "Run Simulation" > "Run Behavioral Simulation". This will launch the Vivado Simulator and compile your design for simulation.

Set Simulation Time: In the Vivado Simulator window, set the simulation time if it's not set automatically. This determines how long the simulation will run.

Run Simulation: Start the simulation by clicking on the "Run" button in the simulation window.

View Results: After the simulation completes, you can view waveforms, debug signals, and analyze the behavior of your design. Logic Diagram :

Logic Gates: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/7ba2fc6a-4435-45e4-9df0-980543aacaea)


Half Adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/407fbd0e-7d46-417b-aea0-2575eae3719b)



Full adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/75d56882-6996-4e35-b539-d8657f5bcd90)




Half Subtractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/bb8566fc-dd1b-4a15-88f2-8c4d7ab931f3)




Full Subtractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/2d039a94-68be-4d06-b251-39a1b7d91e58)




8 Bit Ripple Carry Adder : ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/650d9a6e-171a-405d-aeeb-5609dfa74379)




VERILOG CODE: Logic Gates: module logicgate (a,b,andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate); input a,b;
output andgate,orgate,xorgate,nandgate,norgate,xnorgate,notgate; and(andgate,a,b); or(orgate,a,b); xor(xorgate,a,b); nand(nandgate,a,b); nor(norgate,a,b); xnor(xnorgate,a,b); not(notgate,a); endmodule Half Adder:

module halfadder(a,b,sum,carry); input a,b; output sum,carry; xor g1(sum,a,b); and g2(carry,a,b); endmodule Half Subractor:

module halfsubtractor(a,b,diff,borrow); input a,b; output diff,borrow; xor g1(diff,a,b); and g2(borrow,~a,b); endmodule Full Adder:

module fadd(a,b,c,sum,carry); input a,b,c; output sum,carry; wire w1,w2,w3; xor g1(w1,a,b); and g2(w2,a,b); xor g3(sum,w1,c); and g4(w3,w1,c); or g5(carry,w3,w2); endmodule Full Subtractor:

module fs(a,b,bin,d,bout); input a,b,bin; output d,bout; wire w1,w2,w3; xor g1(w1,b,bin; xor g2(d,w1,a); and g3(w2,a,~w1); and g4(w3,~b,bin); or g5(bout,w2,w3); endmodule 4 bit ripple carry adder:

module rippe_adder(S,Cout,X,Y,Cin); input [3:0] X,Y; input Cin; output [3:0] S; output Cout; wire w1,w2,w3; fulladder u1(S[0],w1,X[0],Y[0],Cin); fulladder u2(S[1],w2,X[1],Y[1],w1); fulladder u3(S[2],w3,X[2],Y[2],w2); fulladder u4(S[3],Cout,X[3],Y[3],w3); endmodule

module fulladder(S,CO,X,Y,Ci); input X,Y,Ci; output S,CO; wire w1,w2,w3; xor G1(w1,X,Y); xor G2(S,w1,Ci); and G3(w2,X,Ci); and G4(w3,X,Y); or G5(CO,w3,w3); endmodule 8 bit ripple carry adder:

module rippe_adder(S,Cout,X,Y,Cin); input [7:0] X,Y; input Cin; output [7:0] S; output Cout; wire w1,w2,w3,w4,w5,w6,w7; fulladder u1(S[0],w1,X[0],Y[0],Cin); fulladder u2(S[1],w2,X[1],Y[1],w1); fulladder u3(S[2],w3,X[2],Y[2],w2); fulladder u4(S[3],w4,X[3],Y[3],w3); fulladder u5(S[4],w5,X[4],Y[4],w4); fulladder u6(S[5],w6,X[5],Y[5],w5); fulladder u7(S[6],w7,X[6],Y[6],w6); fulladder u8(S[7],Cout,X[7],Y[7],w7); endmodule

module fulladder(S,CO,X,Y,Ci); input X,Y,Ci; output S,CO; wire w1,w2,w3; xor G1(w1,X,Y); xor G2(S,w1,Ci); and G3(w2,X,Ci); and G4(w3,X,Y); or G5(CO,w3,w3); endmodule

OUTPUT: Logic gates: 
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/c99d1812-9d34-4af4-ada3-482b37106cbf)


Half adder: 
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/07e34938-ef86-4122-8f99-63ff8587c8bb)


half subtractor:
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/cfc268a9-01d3-44b6-ae9c-6d3f88502bab)


Full Adder: 
![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/933dc3bd-54b6-4998-be85-5f8ed26366b0)


Full Subractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/7689f4fe-f858-4746-b225-06c3a811061a)


4 bit ripple carry adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/64deab3e-9fd4-4644-bcc4-a351b53a4817)


8 bit ripple carry adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/e2a63d2c-1dba-4721-8651-79e2cf757ef1)


RESULT: Hence Logic Gates,Adders and Subtractors are simulated and synthesised using Vivado 2023.1.
