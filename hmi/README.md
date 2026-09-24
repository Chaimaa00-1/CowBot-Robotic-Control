# CowBot Human-Machine Interface (HMI)

## Overview

The CowBot Human-Machine Interface was developed in Python using Tkinter
and deployed on the AIO1101 V3 embedded platform running Ubuntu Linux.

The HMI allows the operator to control and supervise the 6-axis robotic
system through a touchscreen interface.

## Main Features

- Manual control of the six robot axes
- Individual selection of each joint
- Jog+ and Jog- commands
- Joint angle configuration
- Save robot positions
- Load previously saved positions
- Create motion sequences
- Execute saved motion sequences
- Start robot operation
- Stop robot operation
- Robot state supervision

## Robot Axes

| Axis | Joint |
|------|-------|
| J1 | Base |
| J2 | Shoulder |
| J3 | Elbow |
| J4 | Wrist 1 |
| J5 | Wrist 2 |
| J6 | Tool |

## Communication

The HMI communicates with the STM32 controller through a serial UART
connection.

Commands are serialized using JSON structures before being transmitted
to the STM32.

Communication architecture:

HMI (Python / Tkinter)
        |
        | JSON Commands
        v
UART Serial Communication
        |
        v
STM32L431RCT6
        |
        v
Robot Communication Layer

## Data Management

Robot positions and motion sequences can be stored locally and reused
by the operator.

Persistent configuration and position data are managed using a JSON file.

## Linux Deployment

The HMI is deployed on an embedded Linux platform running Ubuntu.

The system was configured for autonomous operation with:

- Full-screen HMI operation
- Automatic application startup
- systemd service configuration
- Software watchdog mechanisms

## Technologies

- Python
- Tkinter
- JSON
- UART
- Ubuntu Linux
- systemd
- Git

## HMI Preview

A preview of the graphical interface is available in the project
documentation.

![CowBot HMI](../docs/cowbot-hmi.png)

## Note

This repository presents the software architecture and functionality of
the CowBot HMI.

Source code developed within the industrial internship environment is not
published in this public repository.
