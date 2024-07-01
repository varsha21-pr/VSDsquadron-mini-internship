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










