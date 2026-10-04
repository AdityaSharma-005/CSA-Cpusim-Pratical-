# CSA-Cpusim-Pratical-
Practical 1: Create a Machine (Basic Computer Architecture)
Aim-> To create, in CPU Sim, a machine based on the Basic Computer architecture: its registers, memory, microinstructions, instruction fields and machine instructions. Tool-> CPU Sim 4.0.11 (Java 8 with JavaFX)
Theory
A CPU Sim machine is described at the register-transfer level by four kinds of objects:

Object	Meaning	Dialog
Hardware modules	Registers, condition bits (single bits that can halt the machine or record a carry) and RAM.	Modify → Hardware Modules (Ctrl+K)
Microinstructions	Elementary register-transfer operations such as PC -> AR, M[AR] -> DR, AC+DR -> AC, a test-and-skip or a decode.	Modify → Microinstructions (Ctrl+Shift+M)
Fetch sequence	The microinstructions executed at the start of every instruction cycle (Practical 2).	Modify → Fetch Sequence (Ctrl+Y)
Machine instructions	A name, an opcode, a format built from fields and an execute sequence of microinstructions ending with End.	Modify → Machine Instructions (Ctrl+M)
A control unit that runs a stored list of microinstructions for each instruction is a microprogrammed control unit, which is exactly what CPU Sim simulates.
