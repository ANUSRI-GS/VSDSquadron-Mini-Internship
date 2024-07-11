# VSDSquadron-Mini-Internship
# TASK 1:
Step 1: Open the terminal window to open the editor named leafpad for writing the C code.

![output](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/880a637e-18a7-4099-abf3-949fea9ed37b)

Step 2: Write the C program for sum of one to n in the terminal 
* To check the result in the terminal window by writing the below command line
  
      gcc s1ton.c
      ls -ltr
* To generate the output by using "./a.out"

![code](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/ac1bd248-68cc-414f-bb88-98869a2bbba3)

Step 3: Compile and run the C code using RISC-V Simulator:
* By using the command line

      cat s1ton.c
* Run the C code by RISC-V Simulator by commanding:

      riscv-unknown-elf-gcc -O1 _mabi=lp64 _march=rv64i -o s1ton.o s1ton.c
      ls -ltr s1ton.o
  
![c1](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/88a26bcd-110b-49e2-ba9e-9b857690317e)

Step 4: Assembly code
* Command line gor generating the assembly code is:

      riscv64-unknown-elf-objdump -d s1ton.o
  
![c2](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/448a122d-4874-413f-b656-f83617bfa740)
![comm2](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/864ecdeb-7526-4fb1-8c5c-050beadf8822)

Step 5: Search the main()

![Screenshot (94)](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/011f3028-21be-493f-af66-dddef2cdaa2e)
![Screenshot (95)](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/33d563d3-8c4c-4ac9-a89f-556639d18f76)
![Screenshot (96)](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/08e0e2af-949a-41dd-af88-60f100d7f1d2)

# TASK 2:
CLOCK CYCLE DIVIDER:

A clock cycle divider (or clock divider) is a circuit that divides the input clock frequency to produce a lower frequency output clock signal. This is commonly used in digital systems to provide different clock rates to various parts of the system that may operate at different speeds.

How a Clock Divider Works?

Basic Division: The simplest form of a clock divider is a counter. For example, a binary counter will toggle its output after a certain number of input clock pulses, effectively dividing the frequency. A divide-by-2 counter will output a clock signal with half the frequency of the input clock.

Flip-Flops: A common way to implement a clock divider is using flip-flops. A D flip-flop can be connected in a toggle mode (where the Q' output is fed back to the D input) to divide the clock frequency by 2.

Frequency Division: By cascading multiple flip-flops or counters, more complex division ratios can be achieved. For example, two cascaded divide-by-2 flip-flops will create a divide-by-4 clock divider.

APPLICATIONS:

* Microcontrollers and Processors: To provide different clock signals for different parts of the system, such as the CPU, memory, and peripherals.
* Communication Systems: To generate clocks for different baud rates in serial communication.
* Timing and Control: To generate specific time intervals for operations in digital systems.

# C code for Clock Cycle Divider:

![VirtualBox_vsdworkshop_25_06_2024_22_09_48](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/e91773f1-f4c3-49c0-916f-05dfbcd4a6ea)

# Output of C code: 
Run the code by using( ./a.out ) :

![VirtualBox_vsdworkshop_25_06_2024_22_27_17](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/7fe4abbf-cfd1-4d44-b3b0-d9a3751820a2)

# Assembly Code:

![VirtualBox_vsdworkshop_25_06_2024_22_34_26](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/47785a34-5af6-4017-9046-22cd501e6959)

![VirtualBox_vsdworkshop_25_06_2024_22_54_12](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/835d33fe-df49-4bbf-a1a3-a6f2a7dbb9fe)

![VirtualBox_vsdworkshop_25_06_2024_22_46_40](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/a96e846e-0b5a-4587-a47a-ea10a69a4f81)


# TASK3: 
STEP 1:To compile C code under the RISC-V architecture and ensure that the output of GCC and RISC-V compilers using following command
       
       spike pk clockcycledivisor.o

![VirtualBox_vsdworkshop_27_06_2024_11_36_19](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/fc4cf358-8c89-4ec3-ad68-ffca3b338718)

STEP 2: Disassemble and compare the ouputs:
Disassemble the output binaries to compare the assembly code. Use the following command

       riscv64_unknown-elf-objdump -d clockcycledivisor.o | less

![VirtualBox_vsdworkshop_27_06_2024_11_36_39](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/8db2fa82-d466-45f2-bdd1-84e0a830e86b)

STEP 3: Debug by using following command

       spike pk -d clockcycledivisor.o
       
To set a breakpoint at the address 0x100b0 in  assembly code and then run the program in a debugger from that point onward using below command

      until pc 0 100b0
      
Find the contents of first counter value a1 using below command

      reg 0 a1

![VirtualBox_vsdworkshop_27_06_2024_11_37_00](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/fdb884e3-785a-48d1-8f05-d8e83a8f384b)

![VirtualBox_vsdworkshop_27_06_2024_11_37_11](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/f45d0239-821e-48c8-a9b4-3d853c66bdb3)

# TASK 4:

Here is the identification of various RISC-V instruction types and the exact 32-bit instruction codes for the given RISC-V instructions:

### R-Type Instructions
R-Type instructions have the format: `opcode[6:0] | rd[11:7] | funct3[14:12] | rs1[19:15] | rs2[24:20] | funct7[31:25]`

1. **ADD r1, r2, r3**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00011| 00010| 000    | 00001| 0110011
   ```
   32-bit instruction: `0000000 00011 00010 000 00001 0110011`

2. **SUB r3, r1, r2**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0100000| 00010| 00001| 000    | 00011| 0110011
   ```
   32-bit instruction: `0100000 00010 00001 000 00011 0110011`

3. **AND r2, r1, r3**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00011| 00001| 111    | 00010| 0110011
   ```
   32-bit instruction: `0000000 00011 00001 111 00010 0110011`

4. **OR r8, r2, r5**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00101| 00010| 110    | 01000| 0110011
   ```
   32-bit instruction: `0000000 00101 00010 110 01000 0110011`

5. **XOR r8, r1, r4**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00100| 00001| 100    | 01000| 0110011
   ```
   32-bit instruction: `0000000 00100 00001 100 01000 0110011`

6. **SLT r10, r2, r4**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00100| 00010| 010    | 01010| 0110011
   ```
   32-bit instruction: `0000000 00100 00010 010 01010 0110011`

7. **SRL r16, r11, r2**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00010| 01011| 101    | 10000| 0110011
   ```
   32-bit instruction: `0000000 00010 01011 101 10000 0110011`

8. **SLL r15, r11, r2**
   ```
   funct7 | rs2  | rs1  | funct3 | rd  | opcode
   0000000| 00010| 01011| 001    | 01111| 0110011
   ```
   32-bit instruction: `0000000 00010 01011 001 01111 0110011`

### I-Type Instructions
I-Type instructions have the format: `imm[11:0] | rs1[19:15] | funct3[14:12] | rd[11:7] | opcode[6:0]`

1. **ADDI r12, r3, 5**
   ```
   imm[11:0]  | rs1  | funct3 | rd  | opcode
   000000000101| 00011| 000    | 01100| 0010011
   ```
   32-bit instruction: `000000000101 00011 000 01100 0010011`

2. **LW r13, r11, 2**
   ```
   imm[11:0]  | rs1  | funct3 | rd  | opcode
   000000000010| 01011| 010    | 01101| 0000011
   ```
   32-bit instruction: `000000000010 01011 010 01101 0000011`

### S-Type Instructions
S-Type instructions have the format: `imm[11:5] | rs2[24:20] | rs1[19:15] | funct3[14:12] | imm[4:0] | opcode[6:0]`

1. **SW r3, r1, 4**
   ```
   imm[11:5] | rs2  | rs1  | funct3 | imm[4:0]  | opcode
   0000000   | 00011| 00001| 010    | 00100     | 0100011
   ```
   32-bit instruction: `0000000 00011 00001 010 00100 0100011`

### B-Type Instructions
B-Type instructions have the format: `imm[12] | imm[10:5] | rs2[24:20] | rs1[19:15] | funct3[14:12] | imm[4:1] | imm[11] | opcode[6:0]`

1. **BNE r0, r1, 20**
   ```
   imm[12] | imm[10:5] | rs2  | rs1  | funct3 | imm[4:1]  | imm[11] | opcode
   0       | 000010    | 00001| 00000| 001    | 0100      | 0       | 1100011
   ```
   32-bit instruction: `0000000 00001 00000 001 0100 0 1100011`

2. **BEQ r0, r0, 15**

        imm[12] | imm[10:5] | rs2  | rs1  | funct3 | imm[4:1]  | imm[11] | opcode
       0       | 000001    | 00000| 00000| 000    | 1110      | 0       | 1100011
   32-bit instruction: `0000000 00000 00000 000 1110 0 1100011`

# TASK 5:

Functional Simulation Experiment Using RISC-V Core Verilog Netlist and Testbench:

* Refer to the following GitHub repositories as a basis for your work:

  * VSD Squadron Mini Internship by Maaz
  * RV32I Implementation by Vinay Rayapati
Use these repositories to clone the necessary files and set up your environment.

* Install and configure GTKWave for waveform visualization. This will allow you to view and analyze the results of your simulation.
* Modify the provided testbench file to suit your specific requirements. Ensure it accurately tests the functionality of your RISC-V core.
* Execute the functional simulation using your simulation tools. Generate waveform snapshots during the simulation to capture the behavior of the RISC-V core.
* After obtaining the waveform snapshots, upload them to your GitHub repository. Ensure they are well-organized and clearly labeled for reference.

![VirtualBox_vsdworkshop_08_07_2024_22_27_49](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/a1f25c30-ecea-42fb-8499-57c3c8cd22f4)

### VERILOG TESTBENCH:

![VirtualBox_vsdworkshop_08_07_2024_20_10_45](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/6c8b5b35-b493-4653-af6a-cf191b777e31)

Use the following command to compile and run the simulation of the Verilog code:

    iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v

To visualize the simulation results, open the waveform using GTKWave with this command:

    gtkwave iiitb_rv32i.vcd

### GTKWAVE WINDOW:

![VirtualBox_vsdworkshop_09_07_2024_11_12_40](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/599b603e-ca72-49ca-92b9-4a113566bfb5)


### Analysing the Output Waveform of various instructions:

* INSTRUCTION 1: `ADD r1,r2,r3`

![VirtualBox_vsdworkshop_09_07_2024_11_35_46](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/373d22a5-2d7d-45dd-b401-84fda558563d)

* INSTRUCTION 2: `SUB r3,r1,r2`

![VirtualBox_vsdworkshop_09_07_2024_11_38_04](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/d576cb54-bc0a-4b51-bc97-690e212f1349)

* INSTRUCTION 3: `AND r2,r1,r3`

![VirtualBox_vsdworkshop_09_07_2024_11_38_26](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/19ef52fc-43d6-43c8-a53c-74749ae32c97)

* INSTRUCTION 4: `OR r8,r2,r5`
  
![VirtualBox_vsdworkshop_09_07_2024_11_39_33](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/e031933c-9016-4d4a-baa0-e5c04908f69c)

* INSTRUCTION 5: `XOR r8,r1,r4`

![VirtualBox_vsdworkshop_09_07_2024_11_39_48](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/2c7590c2-02cc-4253-b7bf-99056afa0a12)

* INSTRUCTION 6: `SLT r10,r2,r4`

![VirtualBox_vsdworkshop_09_07_2024_11_40_02](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/ac18757a-a295-4d28-84c1-5bf700c238b1)

* INSTRUCTION 7: `ADDI r12,r3,5`

![VirtualBox_vsdworkshop_09_07_2024_11_42_31](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/475c8631-4cbe-4da8-b6e3-eb8d7e70c334)

* INSTRUCTION 8: `BEQ R0, R0, 15`

![VirtualBox_vsdworkshop_09_07_2024_11_43_05](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/b99bcc1c-d5c5-4bac-ad4e-919b7030a9e6)

* INSTRUCTION 9: `BNE r0,r1,20`

![VirtualBox_vsdworkshop_09_07_2024_11_45_00](https://github.com/ANUSRI-GS/VSDSquadron-Mini-Internship/assets/160397977/fd708126-55d5-4bee-aeee-9ac1c883d4be)

 # TASK 6:

### Overview

The Clock Cycle Divider project aims to create a digital clock divider circuit using the VSDSquadron Mini, a versatile FPGA development board. The circuit divides the input clock signal to produce lower frequency outputs, useful in various timing applications, including digital signal processing, data acquisition, and embedded systems.

### Components Required:

* VSDSquadron Mini FPGA Board
* Clock Source (External oscillator or onboard clock)
* Breadboard
* Jumper Wires
* Power Supply

### Circuit Connection:

* Clock Source to FPGA: Connect the clock source to the clock input pin on the VSDSquadron Mini. Ensure proper voltage levels matching the FPGA's requirements.
* Output Pins: Configure multiple GPIO pins on the FPGA as clock outputs. Each pin will provide a different divided clock signal.
* Power and Ground: Connect the power supply to the FPGA board and ensure a common ground connection for all components.

### Pinout Diagram:

|Component              	| VSDSquadron Mini Pin  |
|-------------------------|---------------------- |
| Clock Source          	|  Clock Input Pin      |
| Divided Clock Output 1	| GPIO Pin 1            |
| Divided Clock Output 2	| GPIO Pin 2            |
| Power (VCC)            	| VCC                   |
| Ground (GND)	          | GND                   |

### Programming the FPGA:

Define the Clock Divider Logic:

    module ClockDivider(
       input clk,          // Input clock signal
       input reset,        // Reset signal
       output reg clk_out1, // Divided clock output 1
       output reg clk_out2  // Divided clock output 2
    );

    reg [31:0] counter1;
    reg [31:0] counter2;

    // Parameters for division
    parameter DIV_FACTOR1 = 50_000_000; // Adjust for desired frequency
    parameter DIV_FACTOR2 = 25_000_000; // Adjust for desired frequency

    always @(posedge clk or posedge reset) begin
       if (reset) begin
          counter1 <= 0;
          clk_out1 <= 0;
       end else begin
          if (counter1 == DIV_FACTOR1 - 1) begin
              counter1 <= 0;
              clk_out1 <= ~clk_out1;
         end else begin
              counter1 <= counter1 + 1;
         end
       end
    end

    always @(posedge clk or posedge reset) begin
        if (reset) begin
            counter2 <= 0;
            clk_out2 <= 0;
        end else begin
            if (counter2 == DIV_FACTOR2 - 1) begin
                counter2 <= 0;
                clk_out2 <= ~clk_out2;
            end else begin
                counter2 <= counter2 + 1;
            end
         end
      end

    endmodule
    
### Programming and Testing:

* Synthesize and Implement: Use FPGA design software (like Xilinx Vivado) to synthesize and implement the design.
* Generate Bitstream: Create a bitstream file to program the FPGA.
* Upload Bitstream: Use the appropriate tool to upload the bitstream to the VSDSquadron Mini FPGA board.
* Test the Outputs: Verify the divided clock outputs using an oscilloscope or logic analyzer.

### Application and Use Cases:

This Clock Cycle Divider can be used in various applications requiring precise timing control, including:

   * Digital Signal Processing: For creating multiple clock domains with different frequencies.
   * Data Acquisition Systems: To synchronize data collection at different rates.
   * Embedded Systems: Where different subsystems may require different clock frequencies.
This project highlights the capabilities of the VSDSquadron Mini in handling clock management tasks, making it a powerful tool for developing complex digital systems.









  



