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
