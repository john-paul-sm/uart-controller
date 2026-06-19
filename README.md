[![](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)


# UART Controller

A UART controller written in SystemVerilog for supplementing my knowledge of digital design

The goal of this project is to build a complete UART transmit/receive block from the ground up, simulate it, verify the main behavior, and eventually bring it up on an FPGA board (PYNQ-Z2). I will also capture the digital design flow by writing RTL, building testbenches, debugging waveforms, and documenting the design.

---

## Overview

**UART** (*Universal Asynchronous Receiver-Transmitter*) is a serial communication protocol used to transmit data between devices over two wires: TX (transmit) and RX (receive).
Unlike synchronous protocols (SPI, I2C), this protocol is asynchronous and requires no shared clock line to operate. Instead, both devices agree in advance on a prespecified **baud rate**, which is the  number of bits transmitted per second, and use that to stay in sync.

The protocol can be observed like this (from left to right):

| idle | start| data bits | stop |
|:----:|:----:|:----------:|:----:|
|   1  |   0  | d0, d1, d2, ... d7 | 1 |


- The line is held at a logic high when idle.
- A transfer starts with a low start bit
- It will be followed by the 8 data bits, one at a time
- Then it will be followed by a stop bit

For an 8-bit UART frame with no parity and one stop bit, each byte is sent as 10 serial bits total:

**1 start bit + 8 data bits + 1 stop bit**

---

## Components

### Transmitter

### Receiver

### Baud Rate

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

## References

[https://docs.arduino.cc/learn/communication/uart/](https://docs.arduino.cc/learn/communication/uart/)
