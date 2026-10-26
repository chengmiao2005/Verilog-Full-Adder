# Verilog Full Adder

**Verilog · Combinational Logic · Boolean Equations**

A one-bit full-adder exercise. 一位全加器基础实验。

Former repository name: `fulladder`. The original source was stored in `README.md`; it is now preserved without logic changes in [rtl/full_adder.v](rtl/full_adder.v).

## Interface

| Port | Direction | Meaning |
| --- | --- | --- |
| `A`, `B` | Input | One-bit operands |
| `Cin` | Input | Carry input |
| `Sum` | Output | Sum bit |
| `Cout` | Output | Carry output |

The circuit is combinational and requires no clock or reset.

```text
Sum  = A XOR B XOR Cin
Cout = (A AND B) OR (Cin AND (A XOR B))
```

## Truth table

| A | B | Cin | Sum | Cout |
| --- | --- | --- | --- | --- |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 1 | 1 | 0 |
| 0 | 1 | 0 | 1 | 0 |
| 0 | 1 | 1 | 0 | 1 |
| 1 | 0 | 0 | 1 | 0 |
| 1 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 |

## Compilation

With Icarus Verilog installed, run from the repository root:

```bash
mkdir -p build
iverilog -g2012 -s full_adder -o build/full_adder.vvp rtl/full_adder.v
```

This is a compilation command, not a behavioral test. No testbench, FPGA constraints or hardware validation results are included.

For the adder alongside a comparator, see [FPGA Lab 1 — Combinational Logic](https://github.com/chengmiao2005/FPGA-Lab1-Combinational-Logic). The complete coursework index is [FPGA Labs](https://github.com/chengmiao2005/FPGA-Labs).
