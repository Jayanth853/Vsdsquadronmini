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

## Task 5: The Task is to create Verilog Code and Testbench for RISC-V and to verify the Functional Simulation for the Instructions and to generate Waveforms.

The Steps to Create The Waveforms And Functional Verification,

1. The First Process is to Install the iverilog and the Gtkwave for the generation of wave. It's done by the Command,
   sudo apt-get update
   sudo apt-get install iverilog gtkwave

![Screenshot 2024-07-06 102023](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/67f610a0-e3b7-4db0-9fa8-3f6a0e1565eb)

2. Then a directory needs to be created such as Jayanth_rv32i and the verilog code and the testbench are stored in Jayanth_rv32i.v and Jayanth_rv32i_tb.v     
   respectively.
3. The next process is to run and simulate by the command,
   iverilog -o Jayanth_rv32i Jayanth_rv32i.v Jayanth_rv32i_tb.v
4. To get the Output Waveform in GtkWave use the Command,
   ./Jayanth_rv32i.v

 ![Screenshot 2024-07-06 222651](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/aae21175-e59e-4e3a-9d92-c037113722c4)

Now get the Waveform for each Instructions,

## ADD r1,r2,r3

![Gtk_ADD r1,r2,r3](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/51af51ae-3662-4667-bf82-b3e989d129a2)

## SUB r3,r1,r2

![Gtk_SUB r3,r1,r2](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/3a927093-14e3-494b-ac59-161e54fbd4dc)

## AND r2,r1,r3

![Gtk_AND r2,r1,r3](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/583c7b0c-ef16-4923-8863-7e4c78b278e5)

## OR r8,r2,r5

![Gtk_OR r8,r2,r5](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/f5ed1cba-6118-472b-a166-651cb958d1a9)

## XOR r8,r1,r4

![Gtk_XOR r8,r1,r4](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/6d0d0a18-efe0-494a-95c0-a8ebb6aa7392)

## SLT r10,r2,r4

![Gtk_SLT r10,r2,r4](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/03d96e79-b6ea-4e34-b590-225f7362b036)

## ADDI r12,r3,r5

![Gtk_ADDI r12,r3,r5](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/a4a5ffbe-9bea-4e6e-9242-07eb593bcdcc)

## SW r3,r1,r4

![Gtk_SW r3,r1,r4](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/2b6adcb4-fc55-42c4-a41f-6a4370f8bbf7)

## SRL r16,r11,r2

![Gtk_SRL r16,r11,r2](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/0da26479-a4ff-41bf-a74d-902b5a540cc3)

## BEQ r0,r0,15

![Gtk_BEQ r0,r0,15](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/56240575-0631-4900-bf0e-cb61330f57e2)

## BNE r0,r1,20

![Gtk_BNE r0,r1,20](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/98d6982f-2a55-498a-b8f9-c5cee223e0e0)

## BLL r15,r11,r2

![Gtk_BLL r15,r11,r2](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/283ec5fa-4620-4ef7-89e8-7de8c9b5c0a5)

That's the Waveform of The Instructions And the end of 5th Task.

## Task 6: In this task we are developing a project overivew along with the Circuit Digram and their Pin connections.

## Overview

A digital clock divider circuit is a type of electronic circuit used to reduce the frequency of a clock signal. It is commonly employed in digital electronics to generate slower clock signals from a faster one. 
To simplify it, first the circuit recieves an input clock signal with some frequency range and on recieving the Input clock signal the clock divider circuit divides the frequency of the clock signal based on the specified Division Factor.
To understand with this an example, assume that an clock divider circuit recieves an input clock frequency of 100 MHz with a clock division factor of 10 will provide the output frequency of the clock signals as 10 MHz. 

## Connections

1. VSD Squadron Mini Board,
2. Keysight 33210A (Clock Source or Function Generator),
3. SN74LS294 (Clock Frequency Divider),
4. Regulated Power Supply (+5V),
5. Bread Board and Jumper Wires,
6. BNC Connection Cable (for Keysight 33210A).

## Circuit Specifications

1.VSD Squadron Mini Board

The Primary Function of this to provide the required power supply of 5V for the SN74LS294 and also to set the Division Factor with the help of GND and VCC. It also use the divided clock frequency for further process.


![VSD Squadron Mini Board](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/34319042-9735-4031-a770-2e67e318d3cf)


2.Keysight 33210A

The Keysight 33210A is the Clock source or the Function generator which provides the required Square Wave which is fead as the Input Clock Source for the SN74LS294 IC. It has a range of upto 5 - 10 MHz of Frequency.


![Keysight 33210A](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/92c39c8d-420d-44ae-8994-5d68fbe69230)


3.SN74LS294

The SN74LS294 is the Clock Frequency Divider Circuit, which divides the Clock Frequency of the Input Clock which is recieved from the Keysight 33210A, and divides that based on the Binary Values specified in the Programming Input Pins A,B,C,D where D is the MSB and A is the LSB.


![SN74LS294](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/994bdc30-4b59-442f-8af2-fee0441435fb)


## Code 

// Example include for VSD Squadron Mini Board GPIO library

    #include "vsd_gpio.h"

    #define CLK2_PIN  5   // GPIO pin number for CLK2

    #define CLR_PIN   11  // GPIO pin number for CLR

    #define A_PIN     1   // GPIO pin number for A

    #define B_PIN     2   // GPIO pin number for B

    #define C_PIN     15  // GPIO pin number for C

    #define D_PIN     14  // GPIO pin number for D

    void setup() {

    // Initialize GPIO pins as outputs
    
    gpio_init(CLK2_PIN, OUTPUT);
    
    gpio_init(CLR_PIN, OUTPUT);
    
    gpio_init(A_PIN, OUTPUT);
    
    gpio_init(B_PIN, OUTPUT);
    
    gpio_init(C_PIN, OUTPUT);
    
    gpio_init(D_PIN, OUTPUT);
    
    gpio_write(CLK2_PIN, LOW);  
    
    gpio_write(CLR_PIN, HIGH); 
    
    //Example: Set programming inputs for division ratio 10 (A=0, B=1, C=0, D=1)
    
    gpio_write(A_PIN, LOW);
    
    gpio_write(B_PIN, HIGH);
    
    gpio_write(C_PIN, LOW);
    
    gpio_write(D_PIN, HIGH);
    }


    int main() {

    setup();
    
    while (1) {
    
        gpio_write(CLK2_PIN, HIGH);  // Start generating clock signal
        
        delay_ms(1000);  // Example delay for 1 second 
        
        gpio_write(CLK2_PIN, LOW);   // Stop generating clock signal
        
        delay_ms(1000);  // Example delay for 1 second 
    }
    
    
    return 0;
    }


This Code is referred from the AI Tool.

## PIN Connections

1. Keysight 33210A
   1. Connect the Red colour of the BNC Cable to the (CLK 2) Pin 5 of SN74LS294 and Black colour to the (GND) pin 8 of SN74LS294.
   2. The Keysight 33210A is set to Square Wave with the desired Frequency range.

3. SN74LS294
   1. The Pin 5 (CLK 2) is Connected to Red Colour BNC cable which is connected to the output port of the Keysight 33210A.
   2. To prevent circuit from resetting the Pin 11 (CLR Bar) is connected to +5 VCC of the VSD Squadron Mini Board.
   3. The Programming Input Pins, Pin 10 (A), Pin 1 (B), Pin 15 (C), Pin 14 (D) are set to the Binary Values 1010 in the order of Pins D,C,B,A where D is the MSB and A is the LSB. This will set the Dvision Factor to 10.
   4. The Pin 4 (CLK 1) is not used, so it's connect to the +5 VCC of the VSD Squadron Mini Board.
   5. The Pin 7 (Q) Output Pin is Connected to any of the Input Pin here (PD0) of the VSD Squadron Mini Board.
  
3. VSD Squadron Mini Board
   1. The +5 VCC Pin is connected to the Pin 1 (B), Pin 4 (CLK 1), Pin 14 (D), Pin 11 (CLR Bar) of the SN74LS294.
   2. The GND Pin is connected to the Pin 8 (GND), Pin 10 (A), Pin 15 (C).
   3. The PD0 Pin is connected to the Pin 7 (Q).

## Circuit Diagram

The Circuit Diagram for the Digital Clock Divider Circuit using the Keysight 33210A, SN74LS294 and VSD Squadron Mini Board is below.

![Clock Divider Circuit Circuit Diagram](https://github.com/Jayanth853/Vsdsquadronmini/assets/173602478/0bbe69d9-2c24-4274-92a0-106fa85ddc91)

That's the end of Task 6.
