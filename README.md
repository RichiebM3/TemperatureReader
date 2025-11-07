# Temperature Monitoring and Bluetooth Communication Project

## Overview
This project implements a temperature monitoring system using the TM4C123GH6PM microcontroller. It reads temperature data from an ADC and displays the information on an LCD. Additionally, it uses a Bluetooth module (HC-05) to communicate temperature readings wirelessly. The system can respond to commands via Bluetooth to provide real-time temperature data.

## Author
**Richard A Bruce**

## Components
- **Microcontroller:** TM4C123GH6PM
- **LCD Display:** 16x2 LCD
- **Bluetooth Module:** HC-05
- **Temperature Sensor:** Analog temperature sensor connected to ADC
- **Programming Language:** C

## Features
- Real-time temperature monitoring.
- Bluetooth communication for remote access to temperature data.
- LCD display for local viewing of temperature.
- Periodic updates of temperature readings.
- Interrupt-driven architecture for efficient processing.

## Code Structure
The code is organized into several key functions:

### LCD Functions
- **LCD_init()**: Initializes the LCD display.
- **LCD_Cmd()**: Sends commands to the LCD.
- **LCD_write_char()**: Writes a character to the LCD.
- **LCD_string()**: Displays a string on the LCD.

### Bluetooth Functions
- **Bluetooth_init()**: Initializes the Bluetooth module.
- **HC05_Init()**: Configures the HC-05 Bluetooth module for communication.
- **blueTooth_Write()**: Sends a character over Bluetooth.
- **blueTooth_Read()**: Reads a character from Bluetooth.
- **write_string()**: Sends a string over Bluetooth.
- **test_bluetooth()**: Tests Bluetooth communication.

### Temperature Functions
- **ADC_Init()**: Initializes the ADC for temperature readings.
- **get_temperature()**: Retrieves the current temperature from the ADC.

### Timer Functions
- **Timer0A_usd()**: Initializes Timer0 for microsecond delays.
- **Timer1A_msd()**: Initializes Timer1 for millisecond delays.
- **Timer2A_init()**: Initializes Timer2 for periodic temperature updates.

### Interrupt Functions
- **TIMER2A_Handler()**: Handles Timer2 interrupts for periodic temperature updates.

### Main Function
- The `main()` function initializes all peripherals, sets up the LCD, and enters a loop waiting for Bluetooth commands to report the current temperature.

## Setup Instructions
1. **Hardware Setup:**
   - Connect the LCD to the TM4C123GH6PM microcontroller.
   - Connect the HC-05 Bluetooth module to the appropriate UART pins.
   - Connect an analog temperature sensor to the ADC input (e.g., PD1 for AIN0).

2. **Software Setup:**
   - Ensure you have the appropriate development environment set up for programming the TM4C123GH6PM (e.g., Keil, Code Composer Studio).
   - Copy the provided code into your development environment.

3. **Compiling and Uploading:**
   - Compile the code and upload it to the microcontroller using the appropriate programmer.

## Usage Instructions
1. Power on the system.
2. Pair the HC-05 Bluetooth module with your Bluetooth-enabled device.
3. Use a Bluetooth terminal app to connect to the HC-05 module.
4. Send the command `T` or `t` to the microcontroller to request the current temperature.
5. The system will respond with the current temperature and any changes since the last reading.

## Error Handling
- The system includes timeout handling for Bluetooth reads, ensuring that it does not hang indefinitely.
- Temperature readings are processed periodically using interrupts, ensuring timely updates.

## Conclusion
This temperature monitoring and Bluetooth communication project demonstrates the integration of ADC, LCD, and Bluetooth technologies using the TM4C123GH6PM microcontroller. It serves as an excellent introduction to embedded systems programming and wireless communication.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
