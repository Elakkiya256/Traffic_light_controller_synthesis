# Traffic_light_controller_Synthesis

## Aim:

Synthesize Traffic Light Controller design using Constraints and analyse area and Power reports.

## Tool Required:

Functional Simulation: Incisive Simulator (ncvlog, ncelab, ncsim)

Synthesis: Genus

### Step 1: Getting Started

Synthesis requires three files as follows,

◦ Liberty Files (.lib)

◦ Verilog/VHDL Files (.v or .vhdl or .vhd)

### Step 2 : Creating an SDC File

•	In your terminal type “gedit input_constraints.sdc” to create an SDC File if you do not have one.

### Step 3 : Performing Synthesis

The Liberty files are present in the library path,

• The Available technology nodes are 180nm ,90nm and 45nm.

• In the terminal, initialise the tools with the following commands if a new terminal is being used.

◦ csh

◦ source /cadence/install/cshrc

• The tool used for Synthesis is “Genus”. Hence, type “genus -gui” to open the tool.

• Genus Script file with .tcl file Extension commands are executed one by one to synthesize the netlist.

test bench code

`timescale 1 ns / 1 ps

module TrafficLight_tb();

reg rst, clk;
wire [2:0] LED_NS, LED_WE;

TrafficLight L(clk, rst, LED_NS, LED_WE);

initial begin 
clk = 1;
forever #1 clk = ~clk;
end

initial begin
   rst = 1;

#10 rst = 0;

#4000 $finish;
end

endmodule

traffic light.v :

`timescale 1 ns / 1 ps

module TrafficLight_tb();

reg rst, clk;
wire [2:0] LED_NS, LED_WE;

TrafficLight L(clk, rst, LED_NS, LED_WE);

initial begin 
clk = 1;
forever #1 clk = ~clk;
end

initial begin
   rst = 1;

#10 rst = 0;

#4000 $finish;
end

endmodule




Synthesis RTL Schematic :

![Screenshot (126)](https://github.com/user-attachments/assets/4284c0b4-2a3e-4a68-a340-166040b050e1)


Area report:

![Screenshot (128)](https://github.com/user-attachments/assets/982c9668-366e-4295-afe4-1f8ce8dd25e9)


Power Report:

![Screenshot (127)](https://github.com/user-attachments/assets/b9dc2178-7efd-4ccc-bdc8-a7e16f8cc08b)


Result:

The generic netlist of Traffic Light Controller has been created, and area, power reports have been tabulated and generated using Genus.
