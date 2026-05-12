# 32-bit Memory Interfacing for Intel 80486

A hardware design project implementing a 1 MB SRAM memory subsystem for the Intel 80486 microprocessor using 62512 SRAM chips, address decoding logic, and 3:8 decoders.

---

## Overview

This project implements a complete 32-bit SRAM memory interface for the Intel 80486 processor.

The memory subsystem was designed to support:

- 32-bit memory access
- Byte-level write control
- Address decoding
- Multi-bank SRAM organization
- Expandable memory architecture

The system maps 1 MB of SRAM memory starting at address:

12000000H

---

## Hardware Specifications

| Component | Description |
|-----------|-------------|
| Processor | Intel 80486 |
| Data Bus Width | 32-bit |
| Total Memory | 1 MB SRAM |
| SRAM Chip | 62512 (64 KB × 8) |
| Total Chips | 16 |
| Decoder | 74138 (3:8 Decoder) |

---

## Memory Organization

The memory system is divided into:

- 4 memory rows
- 4 byte-wide banks
- 32-bit total data width

### Address Range

| Start Address | End Address |
|---------------|-------------|
| 12000000H | 120FFFFFH |

---

## Address Mapping

### Address Bus Allocation

| Address Lines | Function |
|---------------|----------|
| A31–A20 | Base address decoding |
| A19–A18 | Row selection |
| A17–A2 | Internal SRAM addressing |
| A1–A0 | Replaced by BE0#–BE3# |

---

## Row Selection

A 74138 decoder was used for row selection.

| Row | Address Range |
|-----|---------------|
| Row 0 | 12000000H – 1203FFFFH |
| Row 1 | 12040000H – 1207FFFFH |
| Row 2 | 12080000H – 120BFFFFH |
| Row 3 | 120C0000H – 120FFFFFH |

---

## Design Components

### Master Chip Select Logic

A NAND-based address decoder generates the global chip select signal using upper address bits.

### Byte-Level Write Control

Write operations are controlled using:

- MWTC#
- BE0#
- BE1#
- BE2#
- BE3#

allowing support for:

- 8-bit transfers
- 16-bit transfers
- 32-bit transfers

---

## Processor Connections

| Processor Signal | Connected To |
|------------------|-------------|
| A2–A17 | SRAM A0–A15 |
| A18–A19 | 74138 Decoder |
| D0–D31 | Memory Banks |
| MRDC# | SRAM OE# |
| WR# | SRAM WE# |

---

## Features

- Full 32-bit memory interface
- Byte-addressable memory operations
- Expandable architecture
- No wait-state SRAM access
- Modular bank organization

---

## Tools & Concepts

- Intel 80486 Architecture
- SRAM Memory Systems
- Digital Logic Design
- Address Decoding
- 74138 Decoder Logic

---

## Project Structure

/intel-80486-memory-interface
│── schematic/
│── reports/
│── diagrams/
└── README.md

---

## Results

Successfully designed and verified a complete 1 MB SRAM memory subsystem compatible with the Intel 80486 processor memory architecture.

The design supports efficient byte-level access and scalable memory expansion.

---

## Future Improvements

- FPGA-based implementation
- Larger memory expansion
- Cache memory integration
- PCB-level hardware implementation

---

## References

- Intel 80486 Hardware Reference Manual
- SN74LS138 Decoder Datasheet
- IS62C512 SRAM Datasheet
