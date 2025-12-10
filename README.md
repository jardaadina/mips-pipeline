# MIPS Pipeline Processor

This project implements a **multi-cycle** MIPS processor. It has been tested and validated on the board during laboratory sessions. The processor supports various instruction types, including **Register (R)** and **Immediate (I)** formats.

## Functional Components

The processor consists of the following main modules:

* **Instruction Fetch (IF)** – Instruction extraction.
* **Instruction Decode (ID)** – Instruction decoding.
* **Execution (EX)** – Instruction execution (ALU).
* **Memory (MEM)** – Memory access.
* **Control Unit (UC)** – Manages control signals.
* **Register File (RegFile)** – Stores general-purpose registers.
* **Seven Segment Display (SSD)** – Displays results on the board.
* **Mono-pulse Generator (MPG)** – Input synchronization (Button Debouncer).

**All components have been tested and function correctly.**

## Implemented Instructions

### Register Type (R-Type)

1.  **SRA (Shift-Right Arithmetic)**
    * *Description:* Arithmetic shift to the right.
    * *Format:* `$d = $t >> h`
    * *Machine Code:* `000000 00000 ttttt ddddd hhhhh 000011`

2.  **XOR (Bitwise Exclusive-OR)**
    * *Description:* Logical XOR between two registers.
    * *Format:* `$d = $s ^ $t`
    * *Machine Code:* `000000 sssss ttttt ddddd 00000 100110`

### Immediate Type (I-Type)

1.  **BGTZ (Branch on Greater than Zero)**
    * *Description:* Conditional branch if a register is greater than 0.
    * *Format:* `If $s > 0 then PC = (PC + 4) + (SE(offset) << 2) else PC = PC + 4`
    * *Machine Code:* `000111 sssss 00000 oooooooooooooooo`

2.  **ANDI (AND Immediate)**
    * *Description:* Logical AND between a register and an immediate value.
    * *Format:* `$t = $s & ZE(imm)`
    * *Machine Code:* `001100 sssss ttttt iiiiiiiiiiiiiiii`
