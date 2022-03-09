# Mixed Signal Circuit Design and Simulation Marathon
# 3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit
     • [Abstract](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#abstract) <br />
  • [Reference Circuit Diagram](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-circuit-diagram)<br />
  • [Reference Waveform](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-waveform)<br />
  • [Reference Circuit Details](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-circuit-details)<br />
  • [Software Used](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#software-used)<br />
    • [esim](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#esim)<br />
    • [NgSpice](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#ngspice)<br />
    • [Makerchip](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#makerchip)<br />
    • [Verilator](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#verilator)<br />
  • [Netlists](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#circuit-diagram-in-esim)<br />
  • [Verilog Code](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#verilog-code)<br />
  • [Makerchip](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#makerchip-1)<br />
  • [Makerchip plots](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#makerchip-plots)<br />
  • [Netlists](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#netlists)<br />
  • [NgSpice Plots](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#ngspice-plots)<br />
  • [GAW Plots](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#gaw-plots)<br />
  • [Steps to run generate NgVeri Model](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#steps-to-run-generate-ngveri-model)<br />
  • [Steps to run this project](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#steps-to-run-this-project)<br />
  • [Acknowlegdements](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#acknowlegdements)<br />
  • [References](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#references)<br />

## Abstract
This paper contains implementation of 3-bit Binary counter with Astable multivibrator as clock circuit. A counter is a sequential circuit that goes through a prescribed sequence of states upon the application of input pulses. The counter implemented here is a 3-bit synchronous up counter designed using JK flip flops. It counts binary numbers from 000 to 111. The clock pulses for this counter is produced by a Astable multivibrator. Astable multivibrators generally have a 50% duty cycle that produces a train of square wave pulses at a fixed known frequency.
## Reference Circuit Diagram
![image](https://user-images.githubusercontent.com/82384183/157345801-ba5a2eb3-5052-4cfc-8e3d-a551767f7a40.png) <Br />
Fig 1- 3bit synchronous counter <Br />
![image](https://user-images.githubusercontent.com/82384183/157346232-1ec061df-2cba-4fd8-a481-141f8fc65b47.png)<Br />
Fig 2- Astable multivibrator for clock generation<Br />
## Reference Waveform
![image](https://user-images.githubusercontent.com/82384183/157346332-65b494f1-11b3-43fe-a88a-5f59aa0ec434.png)

## Reference Circuit Details
The block diagram of 3-bit Synchronous binary up counter is shown in fig 1. Synchronous counters have common clock pulses which triggers all the flip-flops simultaneously. The J & K inputs of first, second and third flip-flops are 1, QA , (QA.QB) respectively. The output of JKA flip-flop toggles for every negative edge of clock signal .The output of second JK flip-flop toggles for every negative edge of clock if QA is 1 while that of third toggles for every negative edge of clock if both QA & QB are 1. Here, QC & QA are MSB & LSB respectively. The initial status of the JK flip-flops in the absence of clock signal is QCQBQA=000. This is incremented by one for every negative edge of clock signal. This pattern repeats when further negative edges of clock signal are applied.

The astable multivibrator circuit consists of two switching transistors, a cross-coupled feedback network, and two time delay capacitors which allows oscillation between the two states with no external triggering to produce the change in state. The time period is determined by the time constant of the RC networks connected across the base terminals of the transistors. As the transistors are switching both “ON” and “OFF”, the output at either collector will be a square wave with slightly rounded corners because of the current which charges the capacitors. If the value of the capacitor C1 equals the value of the capacitor, C2, C1 = C2 and also the value of the base resistor R2 equals the value of the base resistor, R3, R2 = R3 then the total length of time of the Multivibrators cycle is given below for a symmetrical output waveform. f=1/T=1/(1.38*R*C). So, for a frequency of 1Hz, we choose the values of R2=R3=100k and C1=C2=7.24µF by the help of the formula.

## Software Used
### eSim
It is an Open Source EDA developed by FOSSEE, IIT Bombay. It is used for electronic circuit simulation. It is made by the combination of two software namely NgSpice and KiCAD.
For more details refer:
https://esim.fossee.in/home
### NgSpice
It is an Open Source Software for Spice Simulations. For more details refer:
http://ngspice.sourceforge.net/docs.html
### Makerchip
It is an Online Web Browser IDE for Verilog/System-verilog/TL-Verilog Simulation. Refer
https://www.makerchip.com/
### Verilator
It is a tool which converts Verilog code to C++ objects. Refer: https://www.veripool.org/verilator/
## Circuit Diagram in eSim
![image](https://user-images.githubusercontent.com/82384183/157348382-02dd4276-01ee-4297-9409-6f6bec41f368.png)

## Verilog Code
```
module vinisha_3bit_counter(input clk, reset, output[2:0] counter);
reg [2:0] counter_up;
always @(negedge clk or posedge reset)
begin
if(reset)
 counter_up <= 3'd0;
else
 counter_up <= counter_up + 3'd1;
end 
assign counter = counter_up;
endmodule
```
## Makerchip
```
\TLV_version 1d: tl-x.org
\SV
/* verilator lint_off UNUSED*/  /* verilator lint_off DECLFILENAME*/  /* verilator lint_off BLKSEQ*/  /* verilator lint_off WIDTH*/  /* verilator lint_off SELRANGE*/  /* verilator lint_off PINCONNECTEMPTY*/  /* verilator lint_off DEFPARAM*/  /* verilator lint_off IMPLICIT*/  /* verilator lint_off COMBDLY*/  /* verilator lint_off SYNCASYNCNET*/  /* verilator lint_off UNOPTFLAT */  /* verilator lint_off UNSIGNED*/  /* verilator lint_off CASEINCOMPLETE*/  /* verilator lint_off UNDRIVEN*/  /* verilator lint_off VARHIDDEN*/  /* verilator lint_off CASEX*/  /* verilator lint_off CASEOVERLAP*/  /* verilator lint_off PINMISSING*/    /* verilator lint_off BLKANDNBLK*/  /* verilator lint_off MULTIDRIVEN*/     /* verilator lint_off WIDTHCONCAT*/  /* verilator lint_off ASSIGNDLY*/  /* verilator lint_off MODDUP*/  /* verilator lint_off STMTDLY*/  /* verilator lint_off LITENDIAN*/  /* verilator lint_off INITIALDLY*/    

//Your Verilog/System Verilog Code Starts Here:
module vinisha_3bit_counter(input clk, reset, output[2:0] counter);
reg [2:0] counter_up;
always @(negedge clk or posedge reset)
begin
if(reset)
 counter_up <= 3'd0;
else
 counter_up <= counter_up + 3'd1;
end 
assign counter = counter_up;
endmodule

//Top Module Code Starts here:
	module top(input logic clk, input logic reset, input logic [31:0] cyc_cnt, output logic passed, output logic failed);
		logic  [2:0] counter;//output
//The $random() can be replaced if user wants to assign values
		vinisha_3bit_counter vinisha_3bit_counter(.clk(clk), .reset(reset), .counter(counter));
	
\TLV
//Add \TLV here if desired                                     
\SV
endmodule
```
## Makerchip plots

![image](https://user-images.githubusercontent.com/82384183/157349714-c77b9291-555a-4633-8bc6-5f845153df4c.png)

## Netlists
```
* C:\Users\SriRamajayam\eSim-Workspace\3bit_counter\3bit_counter.cir

* EESchema Netlist Version 1.1 (Spice format) creation date: 03/09/22 05:44:26

* To exclude a component from the Spice Netlist add [Spice_Netlist_Enabled] user FIELD set to: N
* To reorder the component spice node sequence add [Spice_Node_Sequence] user FIELD and define sequence: 2,1,0

* Sheet Name: /
U1  Net-_U1-Pad1_ Net-_U1-Pad2_ Net-_U1-Pad3_ Net-_U1-Pad4_ Net-_U1-Pad5_ vinisha_3bit_counter		
Q2  clk Net-_C1-Pad2_ GND eSim_NPN		
Q1  GND Net-_C2-Pad2_ Net-_C1-Pad1_ eSim_NPN		
R1  Net-_R1-Pad1_ Net-_C1-Pad1_ 1k		
R4  Net-_R1-Pad1_ clk 1k		
R2  Net-_R1-Pad1_ Net-_C1-Pad2_ 100k		
R3  Net-_R1-Pad1_ Net-_C2-Pad2_ 100k		
C1  Net-_C1-Pad1_ Net-_C1-Pad2_ 7.24u		
C2  clk Net-_C2-Pad2_ 7.24u		
v1  Net-_R1-Pad1_ GND 5		
U4  clk rst Net-_U1-Pad1_ Net-_U1-Pad2_ adc_bridge_2		
U2  clk plot_v1		
U3  rst plot_v1		
v2  rst GND pulse		
U5  Net-_U1-Pad3_ Net-_U1-Pad4_ Net-_U1-Pad5_ out2 out1 out0 dac_bridge_3		
U6  out2 plot_v1		
U7  out1 plot_v1		
U8  out0 plot_v1		

.end
```
## NgSpice Plots
## GAW Plots
## Steps to run generate NgVeri Model
1.Open eSim <Br />
2.Run NgVeri-Makerchip <Br />
3.Add top level verilog file in Makerchip Tab<Br />
4.Click on NgVeri tab<Br />
5.Add dependency files<Br />
6.Click on Run Verilog to NgSpice Converter<Br />
7.Debug if any errors<Br />
8.Model created successfully<Br />
## Steps to run this project
1.Open a new terminal<Br />
2.Clone this project using the following command:

3.Change directory:
cd eSim_project_files/xor_xnor<Br />
4.Run ngspice:
ngspice xor_xnor.cir.out<Br />
5.To run the project in eSim:<Br />
• Run eSim<Br />
• Load the project<Br />
• Open eeSchema<Br />
## Acknowlegdements
1.FOSSEE, IIT Bombay<Br />
2.Steve Hoover, Founder, Redwood EDA<Br />
3.Kunal Ghosh, Co-founder, VSD Corp. Pvt. Ltd. - kunalpghosh@gmail.com<Br />
4.Sumanto Kar, eSim Team, FOSSEE<Br />
## References
[1] https://www.iitg.ac.in/cseweb/vlab/Digital-System-Lab/up_counter.php?id=13<Br />
[2] https://www.electronics-tutorials.ws/waveforms/astable.html

