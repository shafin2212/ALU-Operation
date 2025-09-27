# ALU-Operation
# Verilog ALU (Arithmetic Logic Unit)

This project implements an **8-bit Arithmetic Logic Unit (ALU)** in Verilog, along with a testbench for simulation in **EDAPlayground** or **Icarus Verilog**.

---

## 📘 Features
- 8-bit inputs `A` and `B`
- 16 operations (addition, subtraction, multiplication, division, shift, rotate, logic gates, comparison)
- Testbench included with console monitoring and waveform dumping (`dump.vcd`)

---

## 🛠 Operations Supported

| ALU_Sel | Operation      | Expression          |
|---------|----------------|---------------------|
| 0000    | Addition       | A + B               |
| 0001    | Subtraction    | A - B               |
| 0010    | Multiplication | A * B               |
| 0011    | Division       | A / B               |
| 0100    | Shift Left     | A << 1              |
| 0101    | Shift Right    | A >> 1              |
| 0110    | Rotate Left    | {A[6:0], A[7]}      |
| 0111    | Rotate Right   | {A[0], A[7:1]}      |
| 1000    | AND            | A & B               |
| 1001    | OR             | A \| B              |
| 1010    | XOR            | A ^ B               |
| 1011    | NOR            | ~(A \| B)           |
| 1100    | NAND           | ~(A & B)            |
| 1101    | XNOR           | ~(A ^ B)            |
| 1110    | Greater Than   | (A > B) ? 1 : 0     |
| 1111    | Equal          | (A == B) ? 1 : 0    |

---

## ▶️ Running Simulation

### Using Icarus Verilog:
```bash
iverilog -o alu.out src/ALU.v src/ALU_tb.v
vvp alu.out
gtkwave dump.vcd
