# REAL-TIME EMBEDDED SECURITY

## Aim
To design a Bluetooth-based password authentication system using the STM32F411VET6 microcontroller where a user enters a password through a Bluetooth terminal via the HC‑05 Bluetooth Module. The system verifies the password and displays the status on an SSD1306 OLED Display while controlling LEDs and a buzzer to indicate access granted or denied.

## Components
* hc-05
* oled
* 4 pin push button
* buzzer
* green led
* red led


## Procedure
* The STM32F411VET6 microcontroller communicates with the HC-05 Bluetooth module using UART communication to receive the password from a Bluetooth terminal.
* The STM32F411VET6 microcontroller communicates with the HC-05 Bluetooth module using UART communication to receive the password from a Bluetooth terminal.
* The user enters the password through the Bluetooth terminal connected to the HC-05 module.
* The entered password is displayed on the SSD1306 OLED display for user verification.
* If the password is correct:
* The OLED displays “Access Granted”.
* The green LED turns ON indicating the door is open.
* The current timestamp is sent to the Bluetooth terminal.
* When the push button is pressed, the system waits 5 seconds and then the red LED turns ON, indicating the door is closing.
* If the password is incorrect.
* The buzzer turns ON as an alert.
* The red LED turns ON.
* The OLED displays “Access Denied”.
* After displaying the error message, the system returns to the password entry screen so that the user can try entering the password ag
  

## Connections
### OLED Display (SSD1306 OLED Display – I2C)
https://www.google.com/imgres?q=oled%20ssd1306&imgurl=https%3A%2F%2Fdocs.sunfounder.com%2Fprojects%2Fumsk%2Fen%2Flatest%2F_images%2F27_OLED.png&imgrefurl=https%3A%2F%2Fdocs.sunfounder.com%2Fprojects%2Fumsk%2Fen%2Flatest%2F01_components_basic%2F27-component_oled.html&docid=vagUMotXvaueZM&tbnid=3AXxjSBX9fX5KM&vet=12ahUKEwjoyK_FjqSTAxUkcGwGHX0TF24QnPAOegQIGhAB..i&w=800&h=700&hcb=2&ved=2ahUKEwjoyK_FjqSTAxUkcGwGHX0TF24QnPAOegQIGhAB
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



