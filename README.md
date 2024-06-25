# Vsdsquadronmini
Task 1: The first task in this internship is to install leafpad and all other essential things in virtualbox.
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


Task 2: The second task in the internship is to write a C program for the Clock Divider Circuit The project which i have selected and compile it to Risc Gcc type.
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
