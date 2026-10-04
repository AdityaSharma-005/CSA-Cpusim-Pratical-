# CSA-Cpusim-Pratical-
Practical 1: Create a Machine (Basic Computer Architecture)

Aim-> To create, in CPU Sim, a machine based on the Basic Computer architecture: its registers, memory, microinstructions, instruction fields and machine instructions. Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)

Theory

A CPU Sim machine is described at the register-transfer level by four kinds of objects:

Hardware modules

Microinstructions

Fetch sequence

Machine instructions

A control unit that runs a stored list of microinstructions for each instruction is a microprogrammed control unit, which is exactly what CPU Sim simulates.

Creating a new machine:

<img width="586" height="393" alt="Screenshot 2026-10-04 130611" src="https://github.com/user-attachments/assets/f05d6ea2-4065-46a4-80d2-7a2c5e80fc74" />

Creating the registers:

<img width="832" height="490" alt="Screenshot 2026-10-04 130725" src="https://github.com/user-attachments/assets/e5f5da42-9306-445b-82e3-83394d88c0b9" />

Creating the Condition Bits:

<img width="667" height="646" alt="Screenshot 2026-10-04 130918" src="https://github.com/user-attachments/assets/9d79e0e4-52ab-4af7-8088-756115cb731e" />

Creating the RAM:

<img width="586" height="250" alt="Screenshot 2026-10-04 131025" src="https://github.com/user-attachments/assets/1ba3a782-f7bf-410f-a509-416e523fe82e" />

Creating the microinstructions

TransferRtoR:

<img width="695" height="375" alt="Screenshot 2026-10-04 131202" src="https://github.com/user-attachments/assets/628b3fb4-741e-42fd-a799-2d67e681edac" />

MemoryAccess:

<img width="755" height="266" alt="Screenshot 2026-10-04 131249" src="https://github.com/user-attachments/assets/32fc1519-b391-4452-9b2a-16ec1b1a912e" />

Increment:

<img width="635" height="430" alt="Screenshot 2026-10-04 131341" src="https://github.com/user-attachments/assets/dd630772-eac0-4c66-9641-577dee141256" />

Arithmetic:

<img width="726" height="193" alt="Screenshot 2026-10-04 131441" src="https://github.com/user-attachments/assets/c3a7f68a-9860-4710-8c86-ca3eca37ee33" />

Logical:

<img width="707" height="246" alt="Screenshot 2026-10-04 131518" src="https://github.com/user-attachments/assets/81243402-8359-4822-ab61-404d15d8ebd8" />

Shift:

<img width="600" height="347" alt="Screenshot 2026-10-04 131553" src="https://github.com/user-attachments/assets/a88f36f0-c83b-46a8-98c7-f3dd59d8c079" />

Set:

<img width="648" height="330" alt="Screenshot 2026-10-04 131640" src="https://github.com/user-attachments/assets/133e0410-bfad-4588-a7e1-4fea06b76367" />

Test:

<img width="712" height="333" alt="Screenshot 2026-10-04 131717" src="https://github.com/user-attachments/assets/d7bfedc7-58f1-4913-ae8e-1dbbc4333277" />

Decode:

<img width="765" height="272" alt="Screenshot 2026-10-04 131757" src="https://github.com/user-attachments/assets/f1e41d4a-ea78-4aae-b40d-b659e6d6df6b" />

SetCondBit:

<img width="571" height="166" alt="Screenshot 2026-10-04 131840" src="https://github.com/user-attachments/assets/027075f7-262e-45ac-aa68-f042a1af4a89" />

IO:

<img width="543" height="213" alt="Screenshot 2026-10-04 131930" src="https://github.com/user-attachments/assets/73b2f99f-3b5c-4014-b0be-5411df92864f" />

**Creating the instruction field:**

<img width="871" height="567" alt="Screenshot 2026-10-04 132037" src="https://github.com/user-attachments/assets/4e0f5013-15e0-4c86-9b6c-94d392e31897" />

Creating the machine instructions:

<img width="835" height="613" alt="Screenshot 2026-10-04 132147" src="https://github.com/user-attachments/assets/02471026-d8d8-45ea-bc12-08d02a48fb60" />

Execute sequence of ISZ:

<img width="857" height="566" alt="Screenshot 2026-10-04 132231" src="https://github.com/user-attachments/assets/efc6a361-5d68-4f27-8c28-3ab8606d1b12" />

Result:

A machine based on the Basic Computer architecture was created in CPU Sim and saved as BasicComputer.cpu

Now, we will move onto practical 2, in which there is creation of Fetch sequence, program counter and saving and after that our basic computer will be completed and we can save our machine as BasicComputer.cpu

Practical 2: Create the Fetch Routine of the Instruction Cycle

Aim-> To create the fetch (and decode) routine of the instruction cycle and observe it one microinstruction at a time. Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)


Theory


Every instruction cycle begins with the same fetch and decode phase. In Mano's Basic Computer it takes three clock pulses, controlled by the sequence counter outputs T0, T1 and T2


T0 : AR <- PC T1 : IR <- M[AR], PC <- PC + 1 T2 : D0 ... D7 <- Decode IR(12-14), AR <- IR(0-11), I <- IR(15)

Creating fetch sequence instructions:


<img width="825" height="513" alt="Screenshot 2026-10-04 132654" src="https://github.com/user-attachments/assets/378cf684-1d2b-4c24-ae40-e269a72d076b" />


Testing the routine:
We have opened P03_ADD.a file in CPUSim and set the format of registers to unsigned Dec


<img width="832" height="406" alt="image" src="https://github.com/user-attachments/assets/a7ec841c-062d-4d17-b4d7-37527e5f5146" />

After clicking step by micro 5 times:


<img width="857" height="422" alt="image" src="https://github.com/user-attachments/assets/43eb37f6-75bf-4f6c-bfae-3cacb39d4c38" />

Result:


Observations Table


Micro-step	Microinstruction	AR	PC	IR


start	--	0	0	0


1	PC->AR	0	0	0


2	M[AR]->IR	0	0	63488 (F800)


3	PC+1->PC	0	1	63488


4	IR(0-11)->AR	2048 (800)	1	63488


5	decode-IR	2048	1	63488 -> INP


The fetch routine PC->AR, M[AR]->IR, PC+1->PC, IR(0-11)->AR, decode-IR was created and verified by single-stepping the first instruction of a program.


Practical 3: ADD Operation on Two User-entered Numbers


Aim-> To write an assembly program that reads two numbers entered by the user, adds them and displays the sum. Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)


Theory


INP reads an integer into AC. STA A saves it in memory because the next INP overwrites AC. ADD A is a memory-reference instruction: DR ← M[A], then AC ← AC + DR and the carry out of bit 15 goes to E. OUT displays AC and HLT stops the machine. Numbers are 16-bit two's complement, so the range is −32768 to +32767


programme


; ==============================================================
; Practical 3 : ADD operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : SUM = A + B
; ==============================================================
 INP ; AC <- first number typed by the user
 STA A ; M[A] <- AC (save first number)
 INP ; AC <- second number
 ADD A ; AC <- AC + M[A], E <- carry out
 STA SUM ; M[SUM] <- AC (save the result)
 OUT ; display AC (the sum)
 HLT ; stop
A: .data 1 0 ; first number
SUM: .data 1 0 ; result


after assembling and loading


<img width="942" height="601" alt="Screenshot 2026-10-04 133312" src="https://github.com/user-attachments/assets/e520b500-8863-44f8-a05f-babf2f60da6c" />


after running


<img width="708" height="551" alt="Screenshot 2026-10-04 133344" src="https://github.com/user-attachments/assets/f60355f6-2dec-495f-912b-b85025efcb2d" />

<img width="742" height="238" alt="Screenshot 2026-10-04 133355" src="https://github.com/user-attachments/assets/2ffe7d04-2a78-4c47-a435-7e7d8b69d755" />



Result


The output is correct, program takes the input, stores the input, adds the numbers and displays the sum correctly.

















