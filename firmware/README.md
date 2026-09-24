# STM32 Firmware

## Overview

The STM32 firmware acts as the real-time communication gateway between
the Linux-based Human-Machine Interface (HMI) and the robotic system.

The firmware runs on an STM32L431RCT6 microcontroller and handles
communication between the HMI and the robot through UART, SPI and CAN.

## Communication Flow

HMI (Python / Tkinter)
        |
        | UART / JSON
        v
STM32L431RCT6
        |
        | SPI
        v
MCP2515 CAN Controller
        |
        | CAN
        v
6-Axis Robot

## Main Functions

- Receive commands from the Linux HMI through UART
- Parse JSON-based commands
- Process robot movement requests
- Communicate with the MCP2515 through SPI
- Generate and transmit CAN frames
- Receive robot CAN messages
- Send robot status information back to the HMI

## Hardware

- STM32L431RCT6 microcontroller
- MCP2515 CAN controller
- Embedded Linux AIO1101 V3 board
- 6-axis robotic system

## Communication Interfaces

| Interface | Function |
|-----------|----------|
| UART | Communication between Linux HMI and STM32 |
| JSON | Command and data serialization |
| SPI | Communication between STM32 and MCP2515 |
| CAN | Communication with the robotic system |

## Development Tools

- STM32CubeIDE
- STM32 HAL
- C
- Git

## Note

This repository provides a technical overview of the firmware architecture.

Source code developed within the industrial internship environment is not
published in this public repository.
