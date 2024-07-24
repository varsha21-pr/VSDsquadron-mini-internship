# VSDsquadron-mini-internship
This project includes a simple RISC-V processor core, memory modules, and a basic I/O system.

Let's break down each task:

*Installing Ubuntu on VirtualBox

*Installing Visual C++

*Writing and evaluating example C code along with corresponding RISC-V assembly code

# Command for leafpad and evaluating c
 
$ cd

$ leafpad filename.c &
![task 1](https://github.com/Varsha212003/VSDsquadron--mini-internship/assets/142906031/67581580-bd12-4b3d-aaff-b1903fe6d45c)

# Analyzing the output by different values

$ gcc filename.c

$ ./a.out

![task 2](https://github.com/Varsha212003/VSDsquadron--mini-internship/assets/142906031/327e3dd9-8f2d-4e28-a7cf-75d917f502b6)

# Evaluating RISC-V Assembly

Manually translate the C code to RISC-V assembly.

Alternatively, use a cross-compiler like ' riscv64-unknown-elf-gcc ' to compile the C code to assembly:

![task 3](https://github.com/Varsha212003/VSDsquadron--mini-internship/assets/142906031/567732ef-f60d-4b50-b2ae-18464763f35e)

riscv64-unknown-elf-gcc -S example.c -o example.s

$ riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o filename.o filename.c

$ ls -ltr filename.o

# Simulating the assembly code

![assembly](https://github.com/Varsha212003/VSDsquadron--mini-internship/assets/142906031/6d1f287a-db4f-492a-8240-fa6aed6f7935)


$ riscv64-unknown-elf-objdump -d filename.o //Gives bunch of Code

$ riscv64-unknown-elf-objdump -d filename.o | less // Gives Reduced Code

/main //to view the main function of the code

By following these steps, you can set up your development environment, write, and evaluate C and corresponding RISC-V assembly code effectively




# VSDsquadron---CLOCK--CYCLE--DIVIDER

A clock cycle divider is a circuit that takes an input clock signal and produces an output clock signal with a frequency that is a fraction of the input frequency. This is often used in digital circuits to reduce the frequency of a clock signal for various components.

Here’s a simple example of a C program that simulates a clock cycle divider. This program assumes that the input clock signal is a simple periodic signal, and it divides the clock frequency by a specified factor.

To compile and run the provided C program using RISC-V GCC, follow these steps:

# Save the Program:

Create a file named " clock_divider.c " 

![file 1](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/46d22c2d-abf3-47ca-8c4a-f7857b5d5fac)

![file 2](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/90cfa9e2-3262-405f-b4fa-5d9577081f3e)


# Compile the Program:

When you run the program, it will prompt you to enter a divider value. For example, if you enter 20, the output will look like this:

https://drive.google.com/file/d/1QM4P8uk_5PAlZocckJSuMuQNnpV4NU5L/view?usp=drivesdk

(Another Example)

Enter the divider value: 10
Input clock cycle 0, Output clock state: 0

Input clock cycle 1, Output clock state: 0

...

Input clock cycle 9, Output clock state: 0

Input clock cycle 10, Output clock state: 1

...

Input clock cycle 19, Output clock state: 1

Input clock cycle 20, Output clock state: 0

...

This output shows the state of the output clock for each input clock cycle, simulating a clock divider.

# Use the RISC-V GCC compiler to compile the program. Here’s the command:

" riscv64-unknown-elf-gcc -o clock_divider clock_divider.c "

![file 3](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/5cc5857b-3714-4c32-bd19-bfbe67e49ae1)

![file 4](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/ea5aa3f7-ef7c-43fd-8ee2-cc3fd929ac83)

# Evaluating RISC-V Assembly

![file 5](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/448b0a39-a076-43d4-a6aa-3c1694413ccb)

![file 6](https://github.com/Varsha212003/VSDsquadron---CLOCK--CYCLE--DIVIDER/assets/173601368/2db60ba6-b2ec-42ed-9f60-80441b0efb68)

One common simulator is Spike, the RISC-V ISA Simulator. If you have Spike installed, you can run the program like this:

" spike pk clock_divider "


# SPIKE SIMULATION

Spike is a popular RISC-V ISA simulator often used for running and testing RISC-V binaries

compile your C code with -O1 and -Ofast optimization levels

riscv64-unknown-elf-gcc -O1 -o program_O1 filename.c

riscv64-unknown-elf-gcc -Ofast -o program_Ofast filename.c

![C code with -O1 and -Ofast](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/f16888cb-6193-4273-8783-a1083669769c)


# DEBUG THE SPIKE

 Generate RISC-V Object Dump
 
To inspect the compiled binaries, use riscv64-unknown-elf-objdump:

![DEBUGGING](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/c5b72e2c-ae73-45dc-b872-7c95f1914219)

The RISC-V Proxy Kernel, pk , is a lightweight application execution environment that can host statically-linked RISC-V ELF binaries.
It is designed to support tethered RISC-V implementations with limited I/O capability and thus handles I/O-related system calls by proxying them to a host computer


![running on spike](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/fc7a4884-6646-4852-b30d-2d0d5fad208d)


            

# TASK - 4

"Identify various RISC-V instruction type (R, I, S, B, U, J) and exact 32-bit instruction code in the instruction type format for below RISC-V instructions

ADD r6, r2, r1 SUB r7, r1, r2 AND r8, r1, r3 OR r9, r2, r5 XOR r10, r1, r4 SLT r11, r2, r4 ADDI r12, r4, 5 SW r3, r1, 2 SRL r16, r14, r2 BNE r0, r1, 20 BEQ r0, r0, 15 LW r13, r1, 2 SLL r15, r1, r2

Upload the 32-bit pattern on Github"

Here are the 32-bit instruction codes for the specified RISC-V instructions:

ADD r6, r2, r1: 0x00610133

SUB r7, r1, r2: 0x402081b3

AND r8, r1, r3: 0x00709133

OR r9, r2, r5: 0x005121b3

XOR r10, r1, r4: 0x0040a1b3

SLT r11, r2, r4: 0x004151b3

ADDI r12, r4, 5: 0x00520113

SW r3, r1, 2: 0x0020a023

SRL r16, r14, r2: 0x0020e3b3

BNE r0, r1, 20: 0x01404063

BEQ r0, r0, 15: 0x00e04063

LW r13, r1, 2: 0x00209083

SLL r15, r1, r2: 0x002091b3

# INSTRUCTION FORMATS :

# R-Type: Used for register-register operations.

Fields: opcode, rd, funct3, rs1, rs2, funct7

Format: funct7[6] rs2[5] rs1[5] funct3[3] rd[5] opcode[7]

# I-Type: Used for immediate and load operations.

Fields: opcode, rd, funct3, rs1, imm[11:0]

Format: imm[11:0] rs1[5] funct3[3] rd[5] opcode[7]

# S-Type: Used for store operations.

Fields: opcode, imm[11:5], funct3, rs1, rs2, imm[4:0]

Format: imm[11:5] rs2[5] rs1[5] funct3[3] imm[4:0] opcode[7]

# B-Type: Used for branch operations.

Fields: opcode, imm[12], imm[10:5], funct3, rs1, rs2, imm[4:1], imm[11]

Format: imm[12|10:5] rs2[5] rs1[5] funct3[3] imm[4:1|11] opcode[7]

# U-Type: Used for upper immediate operations.

Fields: opcode, rd, imm[31:12]

Format: imm[31:12] rd[5] opcode[7]

# J-Type: Used for jump operations.

Fields: opcode, rd, imm[20|10:1|11|19:12]

Format: imm[20|10:1|11|19:12] rd[5] opcode[7]

# Decoding Instructions:
# 1) ADD r6, r2, r1

Type: R

funct7 = 0000000, rs2 = 00001, rs1 = 00010, funct3 = 000, rd = 00110, opcode = 0110011

Instruction code: 0000000 00001 00010 000 00110 0110011

# 2) SUB r7, r1, r2

Type: R

funct7 = 0100000, rs2 = 00010, rs1 = 00001, funct3 = 000, rd = 00111, opcode = 0110011

Instruction code: 0100000 00010 00001 000 00111 0110011

# 3) AND r8, r1, r3

Type: R

funct7 = 0000000, rs2 = 00011, rs1 = 00001, funct3 = 111, rd = 01000, opcode = 0110011

Instruction code: 0000000 00011 00001 111 01000 0110011

# 4) OR r9, r2, r5

Type: R

funct7 = 0000000, rs2 = 00101, rs1 = 00010, funct3 = 110, rd = 01001, opcode = 0110011

Instruction code: 0000000 00101 00010 110 01001 0110011

# 5) XOR r10, r1, r4

Type: R

funct7 = 0000000, rs2 = 00100, rs1 = 00001, funct3 = 100, rd = 01010, opcode = 0110011

Instruction code: 0000000 00100 00001 100 01010 0110011

# 6) SLT r11, r2, r4

Type: R

funct7 = 0000000, rs2 = 00100, rs1 = 00010, funct3 = 010, rd = 01011, opcode = 0110011

Instruction code: 0000000 00100 00010 010 01011 0110011

# 7) ADDI r12, r4, 5

Type: I

imm = 000000000101, rs1 = 00100, funct3 = 000, rd = 01100, opcode = 0010011

Instruction code: 000000000101 00100 000 01100 0010011

# 8) SW r3, r1, 2

Type: S

imm = 0000000 (high) 00010 (low), rs2 = 00011, rs1 = 00001, funct3 = 010, opcode = 0100011

Instruction code: 0000000 00011 00001 010 00010 0100011

# 9) SRL r16, r14, r2

Type: R

funct7 = 0000000, rs2 = 00010, rs1 = 01110, funct3 = 101, rd = 10000, opcode = 0110011

Instruction code: 0000000 00010 01110 101 10000 0110011

# 10) BNE r0, r1, 20

Type: B

imm = 000000 (high) 0100 1 (low), rs2 = 00001, rs1 = 00000, funct3 = 001, opcode = 1100011

Instruction code: 0000000 00001 00000 001 000100 1 1100011

# 11) BEQ r0, r0, 15

Type: B

imm = 000000 (high) 0111 0 (low), rs2 = 00000, rs1 = 00000, funct3 = 000, opcode = 1100011

Instruction code: 0000000 00000 00000 000 001110 0 1100011

# 12) LW r13, r1, 2

Type: I

imm = 000000000010, rs1 = 00001, funct3 = 010, rd = 01101, opcode = 0000011

Instruction code: 000000000010 00001 010 01101 0000011

# 13) SLL r15, r1, r2

Type: R

funct7 = 0000000, rs2 = 00010, rs1 = 00001, funct3 = 001, rd = 01111, opcode = 0110011

Instruction code: 0000000 00010 00001 001 01111 0110011

# Clone the repository locally:

git clone <repository_url>

# Navigate into the cloned repository directory:

cd RISC-V-Instructions

Move or copy the downloaded file instruction_codes.txt to the cloned repository directory

git add instruction_codes.txt

# Commit the changes:

git commit -m "Add RISC-V instruction codes with explanations"

# Push the changes to GitHub:

git push origin main .


         
# TASK - 5

Use this RISC-V Core Verilog netlist and testbench for functional simulation experiment and upload the waveforms. 

# STEP-1 - CLONING THE REFERENCE REPOSITORY

     - $ git clone https://github.com/vinayrayapati/rv32i.git my_riscv_project
      
      $ cd my_riscv_project -

![clone](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/0be38494-6c37-412b-ba26-6f30d7dfdba5)

# STEP-2 - SETTING UP THE SIMILATION TOOLS

    -  $ sudo apt update
      
      $ sudo apt install iverilog gtkwave -

![sudo apt](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/62014a93-3119-4054-a121-070f16b921c1)

# STEP-3 - RUN THE FUNCTIONAL SIMULATIONAL

Testbench is configured to dump waveforms into a " .vcd " file.

     -  $ nano iiitb_rv32i_tb.v  -

![file3](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/eec0330a-58db-431b-a178-57c41161352a)

![functional](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/17d49eaf-3e16-4459-b2e1-6637219d02ff)

compile and simulate:

  -  $ iverilog -o rv32i_simulation iiitb_rv32i.v iiitb_rv32i_tb.v
    
    $ vvp rv32i_simulation -
    
gtkwave window will open after commanding the below code

  -  $ gtkwave simulation.vcd     -

![gtk wave window](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/da3c89b8-f194-42e1-86b6-f3b857fbd015)

--> click " + " icon near iiitb_rv32i_tb 
--> rv32 will pop out

# OUTPUT

# ADD:

![ADD](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/ad57ef1c-747b-4b71-888c-072ff97e9715)

# SUB:

![SUB](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/8144d79c-7ba9-4f04-9d9b-e29f9847050a)

# AND:

![AND](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/4c0faceb-95a1-4eab-8ad2-b302aa4739fe)

# OR:

![OR](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/de9c2ddc-51bc-4c88-a25f-4498e53528da)

# XOR:

![XOR](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/2a8c0687-55e2-47b0-96ae-34eac0e73f30)

# SLT:

![SLT](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/9bbdac27-6388-4ca8-a164-8ace2ced13bd)

# BEQ:

![BEQ](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/2956baee-3c0f-4b95-a035-d42196404ff0)

# BNE:

![BNE](https://github.com/varsha21-pr/VSDsquadron-mini-internship/assets/142906031/e122cde8-2144-4c60-a457-a0585f33f5bb)


 # | TASK - 6 |

# PROJECT NAME 
  Clock Cycle Divider: Crafting a Digital Clock Divider Circuit

# OVERVIEW 

The Clock Cycle Divider project aims to design a clock divider using a RISC-V processor. The objective is to divide the frequency of an input clock signal to produce a lower frequency output signal. This clock divider is an essential component in digital systems where timing and frequency control are crucial.The system uses a CH32V003 RISC-V processor to manage the clock signals and interfaces with other digital components for clock signal generation and division.

# Components Required

- RISC-V processor

- Clock signal generator
 
- Breadboard

- Jumper wires

- Power supply

- Oscilloscope or frequency counter (for testing and verification)

- Supporting peripherals and components for the RISC-V processor

# Circuit Connection

1- Connect the input clock signal to the clock input pin of the RISC-V processor.

2- Configure the RISC-V processor to implement the clock divider logic.
 
3- Connect the output pins of the RISC-V processor to the appropriate pins on the breadboard.
 
4- Connect the power supply to the power pins of the RISC-V processor.

5- Use jumper wires to make the necessary connections between components.
 
6- Verify the connections with an oscilloscope or frequency counter to ensure the correct frequency output.

# Table for Pin Connection

| Pin Number | Pin Name        | Connection                        |
|------------|-----------------|---------------------------------  |
| 1          | Clock Input     | Connect to clock signal generator |
| 2          | Vcc             | Connect to power supply (+5V)     |
| 3          | Ground          | Connect to ground                 |
| 4          | Output          | Connect to subsequent circuit     |

# BLOCK DIAGRAM


         +---------------------+
         | Input Clock Signal  |
         +----------+----------+
                    |
                    v
         +----------+----------+
         |    Clock Divider    |
         |   Control Module    |
         +----------+----------+
                    |
                    v
        +-----------+------------+
        | RISC-V Processor Core  |
        +-----------+------------+
                    |
                    v
        +-----------+------------+
        |    Clock Divider       |
        |   Implementation       |
        +-----------+------------+
                    |
                    v
         +----------+-----------+
         |     Output Clock     |
         |      Signal          |
         +----------------------+

Input Clock Signal : The initial clock signal that you want to divide.

Clock Divider Control Module : Handles the configuration and control of the clock divider, potentially programmed via the RISC-V processor.

RISC-V Processor Core : Executes instructions and manages the control flow for dividing the clock signal.

Clock Divider Implementation : The actual hardware or software mechanism that performs the clock division, producing the output clock signal with the desired frequency.

Output Clock Signal : The resulting clock signal after division.

# SAMPLE CODE :

#include <stdio.h>

#include <stdint.h>

// Example input clock frequency in Hz

#define INPUT_CLOCK_FREQ 1000000  // 1 MHz

// Example divide factor

#define DIVIDE_FACTOR 4

// Function to simulate reading an input clock signal

uint32_t readInputClock() {

    static uint32_t count = 0;
    
    return ++count; // Simulating an increasing count as input clock signal
}

// Function to simulate generating an output clock signal

void generateOutputClock(uint32_t count) {

    if (count % DIVIDE_FACTOR == 0) {
    
        printf("Output Clock: %d Hz\n", INPUT_CLOCK_FREQ / DIVIDE_FACTOR);
        
    }
    
}

int main() {

    printf("Input Clock: %d Hz\n", INPUT_CLOCK_FREQ);

    while (1) {
    
        uint32_t inputClock = readInputClock();
        
        generateOutputClock(inputClock);
    }

    return 0;
}

https://drive.google.com/file/d/19iU7fSp0mYUZEq25ZaejWYD5rw64SULw/view?usp=drivesdk

