# REAL-TIME EMBEDDED SECURITY

## Aim
To design a Bluetooth-based password authentication system using the STM32F411VET6 microcontroller where a user enters a password through a Bluetooth terminal via the HC‑05 Bluetooth Module. The system verifies the password and displays the status on an SSD1306 OLED Display while controlling LEDs and a buzzer to indicate access granted or denied.

## Materials Required
STM32F411VET6 development board, HC‑05 Bluetooth Module, SSD1306 OLED Display, 4-pin push button, green LED, red LED, buzzer, resistors, connecting wires, and power supply.

## Procedure
The STM32 microcontroller communicates with the HC-05 module via UART to receive the password from a Bluetooth terminal. The entered password is displayed on the OLED and verified by the system; if correct, access is granted, the green LED turns on, and a timestamp is sent via Bluetooth, after which the door closes (red LED on) after 5 seconds when the push button is pressed. If the password is incorrect, the buzzer and red LED activate and the OLED displays “Access Denied” before returning to the password entry screen.

## Connections
### OLED Display (SSD1306 OLED Display – I2C)
* VCC → 3.3V (STM32)
* GND → GND
* SCL → PB8 (I2C1_SCL)
* SDA → PB9 (I2C1_SDA)

### Bluetooth Module (HC-05 Bluetooth Module – UART)
* VCC → 5V
* GND → GND
* TX → PA10 (USART1_RX)
* RX → PA9 (USART1_TX) (use voltage divider 1kΩ + 2kΩ to step 3.3V)

### Push Button (4-Pin)
* One pin → PA0
* Opposite pin → GND
* Use internal pull-up in the STM32F411VET6.

### Green LED (Access Granted Indicator)
* Anode → PD12 through 220Ω resistor
* Cathode → GND

### Red LED (Door Closed / Access Denied Indicator)
* Anode → PD13 through 220Ω resistor
* Cathode → GND

### Buzzer
* Positive → PD14
* Negative → GND




## References
* STM32F411VET6 Datasheet and Reference Manual – STMicroelectronics documentation for GPIO, UART, and I2C peripheral configuration.
* HC-05 Bluetooth Module datasheet for Bluetooth communication and AT command configuration
* SSD1306 OLED Display controller datasheet for I2C interface and display commands.
* STMicroelectronics application notes and tutorials on UART and I2C communication with STM32 microcontrollers.
* Embedded systems programming guides and online tutorials related to STM32 bare-metal programming and peripheral interfacing



