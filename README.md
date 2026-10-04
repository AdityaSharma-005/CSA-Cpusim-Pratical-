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

















