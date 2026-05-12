
# Custom CPU Design in Verilog

A fully custom CPU architecture designed and implemented in Verilog HDL as part of the ECEN345 Computer Architecture course at Nile University.

## Overview

This project involved designing a complete processor from scratch, including:

- Custom Instruction Set Architecture (ISA)
- Datapath and Control Unit design
- Register File implementation
- Arithmetic and Logical execution modules
- Simulation and verification using Verilog testbenches

The processor was designed for educational low-level computation applications and demonstrates full instruction execution flow.

---

## Features

- Custom ISA specification
- Register-based execution
- Arithmetic and logic instructions
- Memory access operations
- Branching and control flow
- Fully modular HDL design
- Functional verification through simulation

---

## Technologies Used

- Verilog HDL
- ModelSim
- Digital Logic Design
- Computer Architecture Concepts

---

## Architecture

The CPU consists of:

- Program Counter
- Instruction Memory
- Control Unit
- ALU
- Register File
- Data Memory
- Multiplexers and Routing Logic

---

## Verification

Simulation verified:

- Arithmetic instructions
- Register operations
- Control instructions
- Memory transactions
- Instruction decoding correctness

---

## Project Structure

/custom-cpu-verilog
│── src/
│── testbench/
│── diagrams/
│── simulation-results/
└── README.md

---

## Results

Successfully executed custom instruction sequences with correct output validation through waveform analysis.

---

## Future Improvements

- Pipeline implementation
- Hazard detection
- Cache memory integration
- FPGA deployment
