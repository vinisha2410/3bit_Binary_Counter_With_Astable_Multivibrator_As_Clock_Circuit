# Mixed Signal Circuit Design and Simulation Marathon
# 3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit
   • [Abstract](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#abstract) <br />
   • [Reference Circuit Diagram](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-circuit-diagram)<br />
• [Reference Waveform](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-waveform)<br />
• [Reference Circuit Details](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#reference-circuit-details)<br />
• [Software Used](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#software-used)<br />
• [eSim](https://github.com/vinisha2410/3bit_Binary_Counter_With_Astable_Multivibrator_As_Clock_Circuit/blob/main/README.md#esim)<br />
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
## Reference Waveform
## Reference Circuit Details
The block diagram of 3-bit Synchronous binary up counter is shown in fig 1. Synchronous counters have common clock pulses which triggers all the flip-flops simultaneously. The J & K inputs of first, second and third flip-flops are 1, QA , (QA.QB) respectively. The output of JKA flip-flop toggles for every negative edge of clock signal .The output of second JK flip-flop toggles for every negative edge of clock if QA is 1 while that of third toggles for every negative edge of clock if both QA & QB are 1. Here, QC & QA are MSB & LSB respectively. The initial status of the JK flip-flops in the absence of clock signal is QCQBQA=000. This is incremented by one for every negative edge of clock signal. This pattern repeats when further negative edges of clock signal are applied.

The astable multivibrator circuit consists of two switching transistors, a cross-coupled feedback network, and two time delay capacitors which allows oscillation between the two states with no external triggering to produce the change in state. The time period is determined by the time constant of the RC networks connected across the base terminals of the transistors. As the transistors are switching both “ON” and “OFF”, the output at either collector will be a square wave with slightly rounded corners because of the current which charges the capacitors. If the value of the capacitor C1 equals the value of the capacitor, C2, C1 = C2 and also the value of the base resistor R2 equals the value of the base resistor, R3, R2 = R3 then the total length of time of the Multivibrators cycle is given below for a

symmetrical output waveform. f=1/T=1/(1.38*R*C). So, for a frequency of 1Hz, we
 



choose the values of R2=R3=100k and C1=C2=7.24µF by the help of the formula.

## Software Used
### eSim
### NgSpice
### Makerchip
### Verilator
## Circuit Diagram in eSim
## Verilog Code
## Makerchip
## Makerchip plots
## Netlists
## NgSpice Plots
## GAW Plots
## Steps to run generate NgVeri Model
## Steps to run this project
## Acknowlegdements
## References
