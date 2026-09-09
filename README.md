# CANOpener SE

CAN Opener Standard Edition, Hardware Revision A.

![CANOpener SE](docs/images/hero.png)

CANOpener SE is a compact dual CAN bus interface that plugs into a vehicle OBD-II diagnostic port. It is built around an Espressif ESP32-C5-WROOM-1-N8R8 with two independent CAN-FD controllers and two Texas Instruments TCAN3414 transceivers.

The board includes onboard voltage regulation, input and CAN bus protection, an addressable RGB status LED, Boot and Reset controls, and a wireless antenna. It can be powered from the vehicle or from USB-C.

## Documentation

- [Hardware specifications](docs/hardware.md)
- [Hardware documentation PDF](docs/CANOpener-SE-Hardware-Documentation.pdf)

## Highlights

|                   |                                 |
| ----------------- | ------------------------------- |
| MCU               | Espressif ESP32-C5-WROOM-1-N8R8 |
| CAN transceivers  | 2× Texas Instruments TCAN3414   |
| Interfaces        | 2× Classical CAN / CAN FD       |
| Max CAN data rate | 5 Mbps                          |
| Vehicle input     | Up to 24 V (typical 12 V)       |
| USB               | USB-C, 5 V                      |
| Logic             | 3.3 V                           |

## GPIO map

CAN 1 is schematic channel `CAN_0`. CAN 2 is `CAN_1`. GPIO numbers are MCU signals, not module pad numbers.

| Function          | Schematic net | GPIO | Module pad |
| ----------------- | ------------- | ---- | ---------- |
| BOOT button       | BOOT          | 28   | 15         |
| RGB LED data      | RGB_LED       | 2    | 4          |
| CAN 1 RX          | CAN_0_RXD     | 0    | 6          |
| CAN 1 TX          | CAN_0_TXD     | 1    | 7          |
| CAN 2 RX          | CAN_1_RXD     | 7    | 9          |
| CAN 2 TX          | CAN_1_TXD     | 8    | 10         |
| CAN standby (STB) | CAN_STB       | 3    | 5          |
