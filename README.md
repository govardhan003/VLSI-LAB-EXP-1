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

Logic Gates: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/448a661b-da60-4a70-a884-95edfcedcf5c)


Half Adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/e7f6f744-ef80-4e4b-88f0-9f983954e5b4)


Full adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/38258660-baf3-4a0f-a165-587dbb626820)


Half Subtractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/590ee8b7-871d-4207-a392-1cd61ff0fb78)


Full Subtractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/2a84a20e-81d8-46a7-944d-8cc87ece0976)


8 Bit Ripple Carry Adder : ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/7ed40dd2-15c4-4040-b730-5232140dc597)
 

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

OUTPUT: Logic gates: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/e022460c-f552-4585-a171-e3f3d423477e)


Half adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/a2d49acf-2c4b-4f63-8432-4823d0f8aec7)


half subtractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/6701997d-f5f8-43a5-bee0-144cccb63cc9)


Full Adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/bd602c10-ce57-48c6-85b1-874b43423857)


Full Subractor: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/cb6c5934-2a7e-495d-8db1-d66c88640051)


4 bit ripple carry adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/7b1b321c-4e4a-4901-9609-8ca836a9577a)


8 bit ripple carry adder: ![image](https://github.com/navaneethans/VLSI-LAB-EXP-1/assets/165632778/26e5e5c9-2a34-4b96-882e-6c95e3abc562)


RESULT: Hence Logic Gates,Adders and Subtractors are simulated and synthesised using Vivado 2023.1.
