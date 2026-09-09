# CANOpener SE Hardware Specifications

Standard Edition · Hardware Revision A

Original document: [CANOpener-SE-Hardware-Documentation.pdf](CANOpener-SE-Hardware-Documentation.pdf)

## Introduction

CANOpener SE is a compact dual CAN bus interface designed to connect directly to vehicle networks through the OBD-II diagnostic port.

At the heart of CANOpener SE is an Espressif ESP32-C5 microcontroller with two independent CAN-FD controllers and integrated wireless connectivity. Two Texas Instruments TCAN3414 CAN transceivers provide the physical interface between the controller and the vehicle CAN networks.

The device connects directly to two CAN buses available through the OBD-II connector and supports both Classical CAN and CAN FD communication. CANOpener SE can be powered directly from the vehicle or through USB-C for development and configuration.

Onboard voltage regulation, input protection, CAN bus protection, an addressable RGB status LED, and dedicated Boot and Reset controls are integrated into the board.

## Electrical specifications

| Specification | Value |
| --- | --- |
| Vehicle input voltage | Up to 24 V |
| Typical input voltage | 12 V |
| USB input voltage | 5 V |
| Logic / I/O voltage | 3.3 V |
| Operating current | — |
| CAN interfaces | 2 |
| CAN protocols | Classical CAN, CAN FD |
| Maximum CAN data rate | 5 Mbps |

## Hardware overview

![Board features at a glance](images/pcb.png)

### OBD-II pinout

![OBD-II connector](images/obd-pinout.png)

| Pin | Connection | Pin | Connection |
| ---: | --- | ---: | --- |
| 1 | NC | 9 | NC |
| 2 | NC | 10 | NC |
| 3 | CAN 2 High (CAN1) | 11 | CAN 2 Low (CAN1) |
| 4 | GND | 12 | NC |
| 5 | NC | 13 | NC |
| 6 | CAN 1 High (CAN0) | 14 | CAN 1 Low (CAN0) |
| 7 | NC | 15 | NC |
| 8 | NC | 16 | Vehicle Power |

## GPIO reference

ESP32-C5-WROOM-1-N16R8 pin assignments for the BOOT button, addressable RGB LED, dual CAN interfaces, and CAN standby control.

CAN 1 corresponds to schematic channel `CAN_0`; CAN 2 corresponds to `CAN_1`. GPIO numbers identify MCU signals, not module pad numbers.

| Function | Schematic net | GPIO | Module pad |
| --- | --- | ---: | ---: |
| BOOT button | BOOT | 28 | 15 |
| RGB LED data | RGB_LED | 2 | 4 |
| CAN 1 RX | CAN_0_RXD | 0 | 6 |
| CAN 1 TX | CAN_0_TXD | 1 | 7 |
| CAN 2 RX | CAN_1_RXD | 7 | 9 |
| CAN 2 TX | CAN_1_TXD | 8 | 10 |
| CAN standby (STB) | CAN_STB | 3 | 5 |

RX and TX are named from the microcontroller perspective: RX receives data from the CAN transceiver; TX sends data to the CAN transceiver.

The RGB LED uses one data GPIO. The schematic shows a single `CAN_STB` control signal on GPIO3.

## Physical specifications

![Mechanical drawing](images/mechanical.png)

| Dimension | Value |
| --- | --- |
| Overall height | 56.5 mm |
| Connector width | 41.3 mm |
| PCB width | 39.97 mm |
| PCB height | 28.92 mm |
