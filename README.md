# UART Controller

A UART controller written in SystemVerilog for supplementing my knowledge of digital design

The goal of this project is to build a complete UART transmit/receive block from the ground up, simulate it, verify the main behavior, and eventually bring it up on an FPGA board (PYNQ-Z2). I will also capture the digital design flow by writing RTL, building testbenches, debugging waveforms, and documenting the design.

---

## Overview

**UART** (*Universal Asynchronous Receiver-Transmitter*) is a serial communication protocol used to transmit data between devices over two wires: TX (transmit) and RX (receive).
Unlike synchronous protocols (SPI, I2C), UART requires no shared clock line. Instead, both devices agree in advance on a **baud rate**, which is the prespecified number of bits transmitted per second, and use that to stay in sync.

---

## Components

---

## Toolchain

The main open-source toolchain for this project is focused on RTL simulation and waveform debugging.

```text
SystemVerilog  - RTL design and verification
Verilator      - simulation
GTKWave        - waveform viewing
Git/GitHub     - version control and documentation
VS Code        - code editor
```

For FPGA bring-up on the PYNQ-Z2, I plan to use Vivado to synthesize the design, assign FPGA pins, and generate the bitstream. 
