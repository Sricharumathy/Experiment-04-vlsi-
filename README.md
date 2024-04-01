# VLSI LAB EXPERIMENT -04
# SIMULATION AND IMPLEMENTATION OF SEQUENTIAL LOGIC  CIRCUITS                         

## AIM:
To simulate and synthesis SR, JK, T, D - FLIPFLOP, COUNTER DESIGN  using VIVADO

## APPARATUS REQUIRED: 
VIVADO 2023.2

## PROCEDURE:
 STEP:1 Start the Vivado, Select and Name the New project.
 
 STEP:2 Select the device family, device, package and speed. 
 
 STEP:3 Select new source in the New Project and select Verilog Module as the Source type.
 
 STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it.
 
 STEP:5 Select the Behavioural Simulation in the Source Window and click the check syntax.
 
 STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table.
## SR FlipFlop:
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/d0de0037-d9e2-4c51-b5ab-15177feeac84)
## Program
```
end module SRFF(s, r, clk, rst, q);
input s, r, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
case({s, r})
2'b00:q=q;
2'b01:q=1'b0;
2'b10:q=1'b1;
2'b11:q=1'bx;
end
end
endmodule
```
## Output
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/d5a906be-9bc0-4107-a2ae-3c7e59efeb67)


## JK FlipFlop 
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/11b59917-abe6-4b3f-a648-310d55d673af33)
## Program
```
module JKFF(j, k, clk, rst, q);
input j, k, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
case({j, k})
2'b00:q=q;
2'b01:q=1'b0;
2'b10:q=1'b1;
2'b11:q=~q;
endcase
end
end
endmodule
```
## Output
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/3033d244-e2f6-403c-a0e1-197cbf35f10f)

## T FlipFlop
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/0896971a-9a8e-48e6-b111-be3acfc62215)

## Program
```
module TFF(clk, rst, t, q);
input t, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
begin
if(t==0)
q=q;
else
q=~q;
end
end
endmodule
```
## OutPut
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/53853df2-63fe-446c-a756-76801f8197c2)

## D FipFlop

![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/fd84214c-1684-4340-8c50-a3210fd17c96)


## Program
```
module DFF(d, q, clk, rst);
input d, clk, rst;
output reg q;
always@(posedge clk)
begin
if(rst==1)
q=1'b0;
else
q=d;
end
endmodule
```

## Output

![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/a0c8563b-7cae-470f-b7fe-75a926617f4f) 

## Counter:
![image](https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/eb89f242-ed29-4587-a0e3-963c24528fb2)

## Program
```
module Counter(clk,rst,mode,y);
input mode,clk,rst;
output reg [3:0]y;
always@(posedge clk)
begin
if(rst==1)
y=8'b0;
else
begin
if(mode==1)
y=y+1'b1;
else
y=y-1'b1;
end
end
endmodule
```
## Output
<img width="785" alt="image" src="https://github.com/Sricharumathy/Experiment-04-vlsi-/assets/159044760/cbbdfa16-c9cb-4158-8354-200c5d980aad">


## Result
Thus, The FlipFlops and Counter are simulated and verified Successfully.











                      
