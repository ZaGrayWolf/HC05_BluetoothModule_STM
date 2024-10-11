# STM32 UART and GPIO Control

This repository contains the code for controlling an LED using UART communication on an STM32 microcontroller. The project is implemented using the STM32 HAL library, allowing the user to send commands via UART to toggle a GPIO pin connected to an LED.

## Features

- **UART Communication**: Configured on USART1, using interrupt-based reception.
- **GPIO Control**: Toggles the LED connected to GPIO pin PA3.
- **Real-time Feedback**: Received characters are printed back over UART.
- **LED Toggle**: 
  - Sending the character `O` turns the LED on.
  - Sending the character `X` turns the LED off.

## Hardware Requirements

- **STM32 Microcontroller**: Compatible with STM32F4 (e.g., STM32F411CE).
- **LED**: Connected to GPIO pin PA3.
- **UART Interface**: Set up to communicate via USART1.

## Software Requirements

- **STM32CubeIDE**: Or any compatible STM32 development environment.
- **STM32 HAL Library**: The code uses STM32's Hardware Abstraction Layer (HAL).
- **Terminal Application**: To send UART data (e.g., PuTTY, Tera Term).

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ZaGrayWolf/HC05_BluetoothModule_STM.git
cd HC05_BluetoothModule_STM
```

### 2. Open in STM32CubeIDE

1. Open STM32CubeIDE.
2. Import the project into STM32CubeIDE.

### 3. Build and Flash the Code

1. Ensure that the STM32 microcontroller is connected via ST-LINK.
2. Build the project.
3. Flash the binary to the microcontroller.

### 4. Monitor and Control the LED

1. Open a UART terminal (like PuTTY or Tera Term) and connect to the USART1 of the microcontroller.
2. Send the following characters:
   - **`O`**: Turns the LED on.
   - **`X`**: Turns the LED off.

## Code Overview

- **main.c**: The main application file where the system clock, GPIO, and UART are configured.
  - `HAL_UART_RxCpltCallback`: Callback function that processes the received UART data and controls the LED.
  - `__io_putchar`: Used for redirecting `printf()` to the UART.
- **main.h**: Header file with declarations and includes.

### Core Functions

- **SystemClock_Config**: Configures the system clock.
- **MX_GPIO_Init**: Initializes GPIO pin PA3 for output.
- **MX_USART1_UART_Init**: Initializes UART on USART1.
- **HAL_UART_RxCpltCallback**: Handles the received data and toggles the LED.

## Circuit Setup

- **LED**: Connect the anode of the LED to pin PA3 of the STM32, and the cathode to ground via a resistor.
- **UART**: Connect the appropriate UART pins for communication (e.g., TX, RX, GND).

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

### Contributions

Feel free to fork the repository and submit pull requests for any improvements or bug fixes.

