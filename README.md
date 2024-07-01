# Vsdsquadronmini
## Task 1: The first task in this internship is to install leafpad and all other essential things in virtualbox.
The Command for leafpad installation is below,

![Leafpad installation](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/d9462859-293b-4a55-b83a-5d0b23999862)

The next process is to write a sample C program of sum of n numbers from 1 to n,

![Program of sum1ton](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/f664b613-cd6e-4079-96b9-32ba01a745a2)

The output of the above program is below,

![Output of sum1ton](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/e23a3710-5048-45fc-bbfa-959193861e97)

The next step is to convert our C program to risc type by giving the coomand,
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
The compiled risc code is below along with address,

![Calculation of Address Bits](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/841983e5-ee4d-493c-a9e3-4447588cbf54)

That's the end of the first task.


## Task 2: The second task in the internship is to write a C program for the Clock Divider Circuit The project which i have selected and compile it to Risc Gcc type.
First we'll first understand about the Clock Divider circuit,

A clock divider circuit is designed to take an input clock signal and produce an output clock signal with a lower frequency. It divides the frequency of the input clock by a division factor. This is used in digital systems where different components may require different clock speeds.
Let's assume that the division factor is 4, and the output of clock divider is initialized to 0. It takes four clock cycles before the output of the counter equals the dividion counter, 4. When it reaches 4, the output of clock divider turns to 1, and the counter resets itself. It takes another four cycles before the output of the counter equals the division factor, 4. When it reaches 4 again, clk_div turns back to 0. So it takes 8 clock cycles before clk_div goes to 1 and returns to 0 again. As a result, the frequency of clk_div is one eigth of the frequency of original clk.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/bb09628a-4b22-4a3e-a187-865e3783bd24)

The below image is the C Program for the Clock Divider Circuit,

![C Program for Clock Divider Circuit](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/e9d6c455-72fe-4afc-b7b0-8a8eb0c65943)

The Ouptut of the above C Program for Division Factor 4 is,

![Output of Clock Divider Circuit](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/8519f1cb-b731-4908-85cb-3a2c6637ffc7)

The Risc command for Converting the existing C Program to risc type is,
riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o clock_divider.o clock_divider.c
ls -ltr clock_divider.o
The Assembly Code for the Clock Divider Circuit id given by the command,
riscv64-unknown-elf-objdump -d clock_divider.o

![Clock Divider Circuit Assembly Code](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/12cf6635-de3c-46d7-8b4a-fba7d45e467d)

The Reduced Assembly code for the Clock Divider Circuit is done by giving the Command,
riscv64-unknown-elf-objdump -d clock_divider.o | less

![Reduced Assembly Code Of Clock Divider Circuit](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/5df55664-8fef-4daa-8073-e10408f28584)

That's the end of the second task.

## Task 3: In this task we have been instructed to compile the c program with the spike command and observe it with -o1 and -ofast Command.

Spike is the golden reference functional model for the RISC-V ISA, used for simulation and testing of RISC-V software. It is used to compute the output of the program from the Assembly Code Instructions,

The -o1 command is used for moderate and quick level of optimizations for debugging the code.Focuses on reducing code size and improving execution speed without significantly increasing compilation time or altering the program's behavior.

The output of the Clock Divider Circuit with -o1 Command is done by riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o clock_divider.o clock_divider.c,

![Output of Clock Divider with o1 Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/9016519b-142a-4315-ba6c-0bc859cd997f)

The Assembly Code Address with -o1 Command,

![Assembly code Address with o1 Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/c57ebb64-a7ed-4a94-b64a-4f35aa1639ac)

The Assembly Instructions with -o1 and Spike Command,

![Assembly code Instruction with o1 Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/ef1a26d5-6d31-4841-af85-28b526ee4319)

The output of the Clock Divider Ciruit with -o1 Spike Command by spike pk clock_divider.o,

![Output of Clock Divider o1 with Spike Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/05cdb040-7542-477b-a404-af60648bb813)

The -ofast command is used for aggressive optimizations, prioritizes performance over strict compliance and accuracy and may lead to non-standard behavior.Focuses on maximizing performance, often at the cost of increased compilation time and potentially altering program behavior in ways that might break standard performance.

The output of Clock Divider Circuit with -ofast Command riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o clock_divider.o clock_divider.c,

![Output of Clock Divider circuit with oFast](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/30ca3c59-3f21-4588-9988-4bc91e096750)

The Assembly Code Address with -ofast Command,

![Assembly code Instruction with oFast Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/1f1debfa-d9e4-4101-90d8-1b48519c6d84)

The Assembly Level Instruction with -ofast and Spike Command,

![Assembly code Instruction with oFast Spike Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/00d57e65-2dea-4213-bfd6-2836b85fb706)

The output of Clock Divider Circuit with -ofast and Spike Command by spike pk clock_divider.c,

![Outout of Clock Divider Circuit with Spike Command](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/d03e2225-31d1-4607-ae51-d4fea0ba226a)

That's the end of the third task.

## Task 4: In this task the various types of RISC-V Instructions are observed.

The RISC-V Instruction Set Architecture (ISA) is a free and open ISA that provides a set of instructions for designing processors. RISC-V is designed to support a wide range of applications, from small embedded systems to high-performance computing. It is structured into a base integer instruction set and optional extensions.

The two types of Base Integer Instructions,

RV32I: The 32-bit base integer instruction set.

RV64I: The 64-bit base integer instruction set.

RISC-V has several instruction formats, each designed to accommodate different types of operations. 

The main formats include:

R-Type: Used for register-register operations.

I-Type: Used for immediate operations.

S-Type: Used for store operations.

B-Type: Used for branch operations.

U-Type: Used for upper immediate operations.

J-Type: Used for jump operations.

![RISC-V Instruction Formats](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/b3d21b90-a6fc-4f53-90e2-fb6a6817448b)

Let's see in details about the RISC-V Instruction Formats,

R-Type Instruction Format,
The R-Type Instruction Format is used for register-register operations.

The R-Type instruction format consists of six fields:

funct7: A 7-bit field used to specify the function code for the operation.

rs2: A 5-bit field used to specify the second source register.

rs1: A 5-bit field used to specify the first source register.

funct3: A 3-bit field used to specify the function code for the operation.

rd: A 5-bit field used to specify the destination register.

opcode: A 7-bit field used to specify the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/ccd7fb55-0f20-4f39-9567-95086fa229f0)

I-Type Instruction Format,
The I-Type (Immediate-Type) instruction format in the RISC-V architecture is used for instructions that involve an immediate value.This format is used for operations such as load instructions, arithmetic instructions with immediate values.

The I-Type instruction format consists of the following fields:

imm[11:0]: A 12-bit immediate value.

rs1: A 5-bit field specifying the source register.

funct3: A 3-bit field specifying the function code for the operation.

rd: A 5-bit field specifying the destination register.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/71f240af-86f0-4442-93d2-5d1575a943a3)

S-Type Instruction Format,
The S-Type (Store-Type) instruction format in the RISC-V architecture is used for store operations, which involve writing data from a register to memory. This format includes a 12-bit immediate value split across two fields.

The S-Type instruction format consists of the following fields:

imm[11:5]: The upper 7 bits of the 12-bit immediate value.

rs2: A 5-bit field specifying the second source register.

rs1: A 5-bit field specifying the first source register.

funct3: A 3-bit field specifying the function code for the operation.

imm[4:0]: The lower 5 bits of the 12-bit immediate value.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/7425f71f-1aac-441f-90bb-d0bf82e57bba)

B-Type Instruction Format,
The B-Type (Branch-Type) instruction format in the RISC-V architecture is used for conditional branch instructions. This format includes a 12-bit immediate value split across several fields.

The B-Type instruction format consists of the following fields:

imm[12]: The 12th bit of the immediate value.

imm[10:5]: Bits 10 to 5 of the immediate value.

rs2: A 5-bit field specifying the second source register.

rs1: A 5-bit field specifying the first source register.

funct3: A 3-bit field specifying the function code for the operation.

imm[4:1]: Bits 4 to 1 of the immediate value.

imm[11]: The 11th bit of the immediate value.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/48e36c22-b600-4ed4-9925-23be24cae4e8)

U-Type Instruction Format,
The U-Type (Upper Immediate-Type) instruction format in the RISC-V architecture is used for instructions that involve a 20-bit immediate value that is shifted left by 12 bits. This format is used for instructions like LUI (Load Upper Immediate) and AUIPC (Add Upper Immediate to PC).

The U-Type instruction format consists of the following fields:

imm[31:12]: A 20-bit immediate value.

rd: A 5-bit field specifying the destination register.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/f0f1f65d-678f-4f62-a267-b7618b88115d)

J-Type Instruction Format,
The J-Type (Jump-Type) instruction format in the RISC-V architecture is used for jump instructions, such as JAL (Jump and Link), which combines a large immediate value and an offset for branching.

The J-Type instruction format consists of the following fields:

imm[20]: The 20th bit of the immediate value.

imm[10:1]: Bits 10 to 1 of the immediate value.

imm[11]: The 11th bit of the immediate value.

imm[19:12]: Bits 19 to 12 of the immediate value.

rd: A 5-bit field specifying the destination register.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/563e4267-35fa-4485-8b9b-d4b6262d7026)

### Now let's Compute the 32-bit Instruction code for the given Instructions,

## 1.ADD r1,r2,r3
This is a type R-Type Instruction Format.

For the ADD instruction, the fields are as follows:

opcode: 0110011 

rd (destination register): 00001 (r1) 

funct3: 000 

rs1 (source register 1): 00010 (r2) 

rs2 (source register 2): 00011 (r3) 

funct7: 0000000 

Finally, the computed 32-bit Instruction Code is 0000000 00011 00010 000 00001 0110011.

## 2.SUB r3,r1,r2
This is a R-Type Instruction Format.

For the SUB instruction the fields are as follows:

funct7: 0100000

r1: 00010

r2: 00001

funct3: 000

r3: 00011

opcode: 0110011

Finally, the computed 32-bit Instruction Code is 0100000 00010 00001 000 00011 0110011.

## 3.AND r2,r1,r3
The AND instruction is an R-type (register) instruction in the RISC-V ISA.

For the AND instruction the fields are as follows:

opcode: 0110011 

funct3: 111 

funct7: 0000000

rd (r2): 00010

rs1 (r1): 00001

rs2 (r3): 00011

Finally, the computed 32-bit Instruction Code is 0000000 00011 00001 111 00010 0110011.

## 4.OR r8,r2,r5
OR is an R-type instruction in RISC-V.

For the OR instruction the fields are as follows:

funct7: 0000000 

r2: 00101 

r5: 00010 

funct3: 110 

r8: 01000 

opcode: 0110011 

Finally, the computed 32-bit Instruction Code is 0000000 00101 00010 110 01000 0110011.

## 5.XOR r8,r1,r4
The XOR instruction is an R-type instruction.

For the XOR instruction the fields are as follows:

funct7: 0000000 

r1: 00101 

r4: 00010 

funct3: 110 

r8: 01000 

opcode: 0110011 

Finally, the computed 32-bit Instruction Code is 0000000 00100 00001 100 01000 0110011.

## 6.SLT r10,r2,r4
The SLT (Set Less Than) instruction is an R-type (Register) instruction in the RISC-V ISA.

For the SLT instruction the fields are as follows:

funct7: 0000000

rs2: 00100 (binary for 4)

rs1: 00010 (binary for 2)

funct3: 010

rd: 01010 (binary for 10)

opcode: 0110011

Finally, the computed 32-bit Instruction Code is 0000000 00100 00010 010 01010 0110011.

## 7.ADDI r12,r3,5
The RISC-V ADDI instruction is encoded in the I-type Format.ADDI is add immediate instruction.

For the ADDI instruction the fields are as follows:

imm[11:0]: 000000000101 

r3: 00011 

funct3: 000 

r12: 01100 

opcode: 0010011 

Finally, the computed 32-bit Instruction Code is 000000000101 00011 000 01100 0010011.

## 8.SW r3,r1,4
For the instruction SW r3, r1, 4, which stands for "store word", the format typically follows the I-type (Immediate type) format in RISC-V.

For the SW instruction the fields are as follows:

Opcode for SW: This is typically 0100011 in binary for store instructions.

rs2 (r3): Register r3 is encoded as r3 = 3, which in binary for a 5-bit field is 00011.

rs1 (r1): Register r1 is encoded as r1 = 1, which in binary for a 5-bit field is 00001.

Immediate (4): The immediate value 4 needs to be encoded in 12 bits. The binary representation of 4 is 000000000100.

Finally, the computed 32-bit Instruction Code is 0100011 00011 00001 000000000100.

## 9.SRL r16,r11,r2
The RISC-V SRL instruction is encoded in the R-type Format.SRL is Shift Logically Right.

For the SRL instruction the fields are as follows:

opcode: 0b0110011 

rd (destination register r16): 0b10000

rs1 (source register r11): 0b01011

rs2 (source register r2): 0b00010

funct3 (logical right shift): 0b101

funct7 (logical right shift): 0b0000000

Finally, the computed 32-bit Instruction Code is 0000000 00010 01011 101 10000 0110011.

## 10.BNE r0,r1,20
The RISC-V BNE instruction is encoded in the B-type Format.BNE is Branch Not Equal.

For the BNE instruction the fields are as follows:

Opcode: 1100011

Funct3: 001

r0: 00000

r1: 00001

Imm: 000000000010100

Finally, the computed 32-bit Instruction Code is 1100011 001 00000 00001 000000010100.

## 11.BEQ r0,r0,15
In the RISC-V instruction set architecture (ISA), the instruction BEQ r0, r0, 15 stands for "Branch if Equal" and it's a I-Type Format.

For the BEQ instruction the fields are as follows:

Opcode (1100011): 0001100 00000 000 00000

rs1 (r0): 00000

rd (r0): 00000 

funct3 (BEQ): 000 

Immediate (15): 000000000001111 (12 bits, sign-extended to 32-bit)

Finally, the computed 32-bit Instruction Code is 000000001111 00000 000 00000 0001100.

## 12.LW r13,r11,2
In the RISC-V architecture, the LW (Load Word) instruction typically follows the I-type Format.

For the BEQ instruction the fields are as follows:

Opcode: 0000011

Source Register (r11): 1011

Destination Register (r13): 1101

Immediate Value (2): 000000000010

Finally, the computed 32-bit Instruction Code is 0000011 01011 01101 000000000000010.

## 13.SLL r15,r11,r2
RISC-V typically uses the R-type format for arithmetic/logical instructions like SLL.SLL is Shift Logical Left.

For the SLL instruction the fields are as follows:

funct7: 0000000

rs2: 00010

rs1: 00011

funct3: 001

rd: 01111

opcode: 0110011

Finally, the computed 32-bit Instruction Code is 0000000 00010 00011 001 01111 0110011.

That's the end of the 4th task.
