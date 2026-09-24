# CowBot – Robotic Control Unit

## Overview

CowBot is a robotic control unit developed as part of an engineering
internship project.

The system combines an embedded Linux Human-Machine Interface (HMI),
an STM32 real-time communication gateway, and CAN communication
to control and supervise a 6-axis robotic system.

The objective of the project was to design a compact and modular
control architecture integrating embedded software, industrial
communication and robot supervision.

---

## System Architecture

The CowBot architecture combines:

- A Linux-based HMI running on an AIO1101 V3 embedded platform
- An STM32L431RCT6 microcontroller acting as a real-time gateway
- UART/JSON communication between the HMI and STM32
- SPI communication with an MCP2515 CAN controller
- CAN communication with the 6-axis robotic system
- An interface for PLC integration

📄 **[View the complete CowBot System Architecture (PDF)](docs/cowbot-architecture.pdf)**

---

## Human-Machine Interface

The HMI was developed in Python using Tkinter and deployed on
an embedded Linux platform.

### Main Functions

- Manual control of the six robot joints
- Jog+ and Jog- control
- Joint angle configuration
- Save and load robot positions
- Create motion sequences
- Execute saved sequences
- Start and stop commands
- Robot state supervision

<p align="center">
  <img src="docs/cowbot-hmi.png"
       alt="CowBot Human-Machine Interface"
       width="800">
</p>

---

## Embedded Firmware

The STM32L431RCT6 acts as the communication gateway between
the Linux HMI and the robotic system.

### Communication Flow

HMI (Python / Tkinter)  
↓  
UART / JSON  
↓  
STM32L431RCT6  
↓  
SPI  
↓  
MCP2515  
↓  
CAN  
↓  
6-Axis Robot

---

## Technologies

### Embedded Systems

- STM32L431RCT6
- C
- STM32 HAL
- MCP2515
- CAN
- UART
- SPI

### Software

- Python
- Tkinter
- JSON
- Git

### Operating System

- Ubuntu Linux
- systemd
- Automatic application startup
- Software watchdog

---

## Project Structure

```text
CowBot-Robotic-Control/
│
├── README.md
│
├── docs/
│   ├── README.md
│   ├── cowbot-architecture.pdf
│   └── cowbot-hmi.png
│
├── firmware/
│   └── README.md
│
└── hmi/
    └── README.md
