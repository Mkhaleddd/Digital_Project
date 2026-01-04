# Digital IIR Filter Design Project

**Ain Shams University**
**Faculty of Engineering – ECE Dept.**
**Course:** Digital Circuits (ECE 311s) – Fall 2025
**Instructor:** Prof. Sameh A. Ibrahim

---

## Project Overview

This project involves the design and implementation of a **1st-order digital Infinite Impulse Response (IIR) filter** using **VHDL/Verilog** and **Cadence** for circuit-level simulations. The filter processes 4-bit signed input data and produces an 8-bit output using a recursive feedback loop.

IIR filters are widely used in **signal processing**, including audio enhancement, communications, and control systems. Their key feature is the **infinite impulse response**, achieved through feedback, allowing sharp frequency cutoffs with a low filter order. Stability and phase distortion are the main challenges due to feedback.

---

## Repository Structure

| Folder/File     | Description                           |
| --------------- | ------------------------------------- |
| `3NAND`         | Three-input NAND gate implementation  |
| `4x4multiplier` | 4x4-bit multiplier implementation     |
| `8x8multiplier` | 8x8-bit multiplier implementation     |
| `AND`           | AND gate implementation               |
| `Dflipflop`     | Standard D Flip-Flop implementation   |
| `Dflipflop_new` | Modified D Flip-Flop implementation   |
| `FASIGNED`      | Full adder for signed numbers         |
| `FILTER2`       | IIR filter implementation (top-level) |
| `FULLADDER`     | Full adder module                     |
| `HALFADDER`     | Half adder module                     |
| `MULTIPLIER`    | Generic multiplier module             |
| `NAND`          | NAND gate implementation              |
| `NOR`           | NOR gate implementation               |
| `NOT`           | NOT gate implementation               |
| `OR`            | OR gate implementation                |

---

## Design Specifications

* **Inputs/Outputs:** 4-bit signed input (`x[n]`), 8-bit output (`y[n]`)
* **Internal Widths:** 8-bit registers and adders
* **Coefficient Handling:** 4-bit signed, truncate 4 LSBs after multiplication for stability
* **Clock & Reset:** Active-low asynchronous Reset, 10 MHz initial clock
* **Technology:** 130 nm CMOS, VDD = 1.2V
* **Load:** 500 fF at filter output
* **Implementation:** CMOS

---

## Test Cases

1. **Low-Pass Filter**

   * Coefficients: `b0 = 3, b1 = 0, a1 = 4`
   * Input: Step signal from 0 → 5

2. **High-Pass Filter**

   * Coefficients: `b0 = 2, b1 = -2, a1 = -4`
   * Input: Step signal from 0 → 5

3. **Impulse Response**

   * Coefficients: `b0 = 3, b1 = 3, a1 = 7`
   * Input: Single pulse `x[0] = 5`

4. **Smoothing Rapid Changes**

   * Coefficients: `b0 = 1, b1 = 1, a1 = 4`
   * Input: Toggle `x[n]` between 2 and 6 each clock

5. **Overflow Failure**

   * Coefficients: `b0 = 7, b1 = 7, a1 = 6`
   * Input: Step signal from 0 → 7


