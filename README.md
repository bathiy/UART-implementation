# EN2111 Module Assignment Project

This repository contains the Verilog-based digital design project completed as part of the **EN2111 – Electronic Circuit Design** module. The project demonstrates a practical application of UART communication and 7-segment display control using switch inputs.

## 🔧 Project Overview

The goal of this project is to:
- Read 4-bit data input from switches (active-high).
- Append 4 leading zero bits to form an 8-bit data word.
- Send this 8-bit data over UART at 115200 baud rate.
- Display the received hexadecimal value on a 7-segment display.
- Transmit a number and reciveback multiply by two

### Key Features
- **UART Transmitter** with customizable baud rate.
- **Switch-based input (SW[3:0])**, padded to 8-bit word format.
- **Active-high 7-segment decoder** to show hexadecimal values.
- Fully implemented in Verilog and simulated using ModelSim.

## 💻 Files Included

| File                         | Description                                                                 |
|------------------------------|-----------------------------------------------------------------------------|
| `uart_tx.v`                  | UART **Transmitter** module, sends 8-bit data serially at 115200 baud rate |
| `uart_rx.v`                  | UART **Receiver** module, receives 8-bit serial data                        |
| `seg7_decoder.v`             | **7-Segment Decoder** (active-high) that displays 4-bit input in hex format |
| `invert_uart_transceiver.v` | **Top module** integrating TX, RX, switch input, and 7-segment output       |
| `invert_uart_transceiver_test.v` | **Testbench** to simulate and verify the full design behavior         |

---


## 🧠 Technologies Used

- Verilog HDL
- Quartus Prime(for synthesis)
- ModelSim (for simulation)
- FPGA Board(DE0 Nano)

## ⚙️ How It Works

1. User sets a 4-bit input on switches `SW[3:0]`.
2. The design concatenates `4'b0000` as upper bits → `8'b0000xxxx`.
3. The `uart_tx` module sends this 8-bit data serially at 115200 baud.
4. The 7-segment decoder displays the lower nibble of the transmitted data (i.e., switch input) in hexadecimal format.



1. User sets a 4-bit input on switches `SW[3:0]`.
2. The design concatenates `4'b0000` as upper bits → `8'b0000xxxx`.
3. The `uart_tx` module sends this 8-bit data serially at 115200 baud.
4. The 7-segment decoder displays the lower nibble of the transmitted data (i.e., switch input) in hexadecimal format.

