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


Practical 4: SUBTRACT Operation on Two User-entered Numbers


Aim-> To write an assembly program that reads two numbers A and B and displays A − B. Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)


Theory


The Basic Computer has no subtract instruction. Subtraction uses the two's complement: A − B = A + (B′ + 1). CMA forms the 1's complement B′ and INC adds 1, giving −B, which is then added to A with ADD.


Program


; ==============================================================
; Practical 4 : SUBTRACT operation on two user-entered numbers
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Logic : DIFF = A - B = A + (2's complement of B)
; 2's complement of B = B' + 1 (CMA, then INC)
; ==============================================================
 INP ; AC <- A (minuend)
 STA A ; M[A] <- AC
 INP ; AC <- B (subtrahend)
 CMA ; AC <- AC' (1's complement of B)
 INC ; AC <- AC + 1 (2's complement of B = -B)
 ADD A ; AC <- A + (-B) = A - B
 STA DIFF ; M[DIFF] <- AC
 OUT ; display the difference
 HLT
A: .data 1 0 ; minuend
DIFF: .data 1 0 ; result


After assembling and loading the program


<img width="850" height="477" alt="Screenshot 2026-10-04 133705" src="https://github.com/user-attachments/assets/a074c957-a053-4494-a10a-e194070be607" />


Output after running the program and entering both numbers


<img width="846" height="270" alt="Screenshot 2026-10-04 133757" src="https://github.com/user-attachments/assets/8ffd881e-5a3e-4056-8858-020019ad5ae6" />


Result



The output is correct, program takes the input, stores the input, subtracts the numbers using 2's complement method and displays the difference correctly.


Practical 5: Logical Operations: AND, OR, NOT, XOR, NOR, NAND



Aim To write an assembly program that performs AND, OR, NOT, XOR, NOR and NAND on two userentered numbers. Tool CPU Sim 4.0.11 (Java 8 with JavaFX)


Theory


The Basic Computer provides only two logic instructions: AND (memory-reference, AC ← AC ∧ M[addr]) and CMA (register-reference, AC ← AC′). Since {AND, NOT} is functionally complete, every other operation can be built from them with Boolean algebra, applied to all 16 bits at once:


Operation	Boolean identity used	Instruction sequence


A AND B	A·B	LDA A, AND B

A OR B	(A′·B′)′ (De Morgan)	LDA B, CMA, STA NB, LDA A, CMA, AND NB, CMA

NOT A	A′	LDA A, CMA

A XOR B	(A + B)·(A·B)′	LDA RAND, CMA, AND ROR
A NOR B	(A + B)′	LDA ROR, CMA

A NAND B	(A·B)′	LDA RAND, CMA

Program


; ==============================================================
; Practical 5 : Logical operations AND, OR, NOT, XOR, NOR, NAND
; on two user-entered numbers A and B
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; The Basic Computer has only two logic instructions:
; AND (memory-reference) AC <- AC ^ M[addr]
; CMA (register-reference) AC <- AC'
; AND + NOT is a functionally complete set, so every other
; operation is built from them with Boolean algebra:
; NAND = (A.B)'
; OR = (A'.B')' (De Morgan)
; NOR = (A + B)'
; XOR = (A + B) . (A.B)'
; Outputs appear in this order: AND, OR, NOT A, NOT B, XOR, NOR, NAND
; ==============================================================
 INP ; AC <- A
 STA A
 INP ; AC <- B
 STA B
; ---------- AND = A . B ----------------------------------------
 LDA A ; AC <- A
 AND B ; AC <- A . B
 STA RAND
 OUT ; output 1 : A AND B
; ---------- OR = (A' . B')' ------------------------------------
 LDA B
 CMA ; AC <- B'
 STA NB ; NB <- B'
 LDA A
 CMA ; AC <- A'
 STA NA ; NA <- A'
Computer System Architecture – CPU Sim Lab Manual
Page 30
 AND NB ; AC <- A' . B'
 CMA ; AC <- (A' . B')' = A + B
 STA ROR
 OUT ; output 2 : A OR B
; ---------- NOT A, NOT B ---------------------------------------
 LDA NA
 OUT ; output 3 : NOT A
 LDA NB
 OUT ; output 4 : NOT B
; ---------- XOR = (A + B) . (A . B)' ---------------------------
 LDA RAND
 CMA ; AC <- (A . B)' = NAND
 STA RNAND
 AND ROR ; AC <- (A + B) . (A . B)'
 STA RXOR
 OUT ; output 5 : A XOR B
; ---------- NOR = (A + B)' -------------------------------------
 LDA ROR
 CMA ; AC <- (A + B)'
 STA RNOR
 OUT ; output 6 : A NOR B
; ---------- NAND = (A . B)' ------------------------------------
 LDA RNAND
 OUT ; output 7 : A NAND B
 HLT
A: .data 1 0
B: .data 1 0
NA: .data 1 0 ; A'
NB: .data 1 0 ; B'
RAND: .data 1 0 ; A AND B
ROR: .data 1 0 ; A OR B
RXOR: .data 1 0 ; A XOR B
RNOR: .data 1 0 ; A NOR B
RNAND: .data 1 0 ; A NAND B


After assembling and loading the program


<img width="872" height="538" alt="Screenshot 2026-10-04 134019" src="https://github.com/user-attachments/assets/a72f2446-c108-4d66-be76-4b3169b06d09" />


Output after running the program and entering both numbers

<img width="840" height="332" alt="Screenshot 2026-10-04 134116" src="https://github.com/user-attachments/assets/4648307b-03e9-4f9c-b9e5-01919d32c580" />


Result


The program runs and takes both inputs correctly and stores them, All six logical operations were simulated using only AND and CMA. For A = 12 and B = 10 the outputs are AND = 8, OR = 14, NOT A = −13, NOT B = −11, XOR = 6, NOR = −15, NAND = −9

Practical-6 Memory-reference Instructions: ADD, LDA, STA, BUN, ISZ

Aim	To write an assembly program that simulates the memory-reference instructions ADD, LDA, STA, BUN and ISZ.

Tool CPU Sim 4.0.11 (Java 8 with JavaFX)


Theory 


A memory-reference instruction has an opcode 0–6 and a 12-bit address. During fetch AR ← IR(0–11), so at T4 onwards AR holds the address of the operand (the effective address, since I = 0).


Programme



; ==============================================================
; Practical 6 : Memory-reference instructions ADD, LDA, STA, BUN, ISZ
; Machine : BasicComputer.cpu (Mano's Basic Computer)
;
; Task : multiply X by N using repeated addition.
; PROD = X + X + ... + X (N times)
; CTR holds -N; ISZ adds 1 to it on every pass and
; skips the BUN when it reaches 0, ending the loop.
; Data : X = 5, N = 3 (CTR = -3) -> PROD = 15
; ==============================================================
LOOP: LDA PROD ; AC <- M[PROD]
 ADD X ; AC <- AC + M[X]
 STA PROD ; M[PROD] <- AC
 ISZ CTR ; M[CTR] <- M[CTR] + 1; skip next if it became 0
 BUN LOOP ; PC <- LOOP (repeat)
 LDA PROD ; AC <- final product
 HLT
X: .data 1 5 ; multiplicand
CTR: .data 1 -3 ; -N (loop counter)
PROD: .data 1 0 ; product

After Assembling and loading the program

<img width="809" height="492" alt="1000121734" src="https://github.com/user-attachments/assets/c0476b41-450e-4ad5-b009-a13131e76bd1" />

After step 4 in debug mode:

![1000121735](https://github.com/user-attachments/assets/3d26e96e-4d66-493f-b480-d5e9f33c2477)

After step 5 

<img width="822" height="564" alt="1000121736" src="https://github.com/user-attachments/assets/db18de08-217e-4e14-9f2b-56b0dd21c89e" />

After step 14 

<img width="784" height="625" alt="1000121737" src="https://github.com/user-attachments/assets/d95377af-6bee-4db5-8e3d-2f0e30a3a191" />

After Step 16

<img width="830" height="810" alt="1000121738" src="https://github.com/user-attachments/assets/6a39487a-612e-4e7f-a5b5-c2e0a794e154" />

Result

The memory-reference instructions were simulated: LDA, ADD and STA computed the running product, ISZ counted the passes and skipped the branch when the counter reached zero, and BUN formed the loop. Final AC = PROD = 15.

Practical-7 Register-reference Instructions: CLA, CMA, CME, HLT

Aim :- To simulate the register-reference instructions CLA, CMA, CME and HLT and determine AC, E, PC, AR and IR in decimal after execution.

Tool :- CPU Sim 4.0.11 (Java 8 with JavaFX)

Theory


Register-reference instructions have the code 7xxx: opcode 111 with I = 0. The low 12 bits select one operation on AC or E, executed at T3, with no memory access. Because the fetch routine always performs AR ← IR(0–11), AR ends up holding the low 12 bits of the instruction code (for example 800 hex = 2048 for CLA).



Programme 

; ==============================================================
; Practical 7 : Register-reference instructions CLA, CMA, CME, HLT
; Machine : BasicComputer.cpu (Mano's Basic Computer)
; Observe AC, E, PC, AR and IR (Decimal) after every instruction.
; ==============================================================
 LDA NUM ; set-up: AC <- 25 so that CLA has something to clear
 CLA ; 7800 : AC <- 0
 CMA ; 7200 : AC <- AC' (0000 -> FFFF = -1)
 CME ; 7100 : E <- E' (0 -> 1)
 HLT ; 7001 : S <- 1 (halt)
NUM: .data 1 25

After assembling and loading the program

<img width="795" height="377" alt="1000121745" src="https://github.com/user-attachments/assets/b8ebf1d5-2e17-43be-be41-e20642c527b0" />

After step 1:LDA NUM: AC = 25

<img width="823" height="710" alt="1000121747" src="https://github.com/user-attachments/assets/f89ec106-655b-4558-b161-660a1e0b968c" />

After step 2:CLA: AC = 0, AR = 2048 (800 hex

<img width="829" height="767" alt="1000121748" src="https://github.com/user-attachments/assets/011ba4aa-c93f-4fb1-847d-59d882a0720b" />

After step 3:CMA: AC = 65535 (FFFF hex = −1), AR = 512

<img width="807" height="874" alt="1000121749" src="https://github.com/user-attachments/assets/58525cd1-1e8f-4847-9feb-e15d8aaecef0" />



























