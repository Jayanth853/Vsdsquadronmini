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




