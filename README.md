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
![download](https://github.com/user-attachments/assets/aaac933d-fd4d-49bf-8d40-5c63d4d7d186)

* VCC → 3.3V (STM32)
* GND → GND
* SCL → PB8 (I2C1_SCL)
* SDA → PB9 (I2C1_SDA)

### Bluetooth Module (HC-05 Bluetooth Module – UART)
<img width="236" height="213" alt="image" src="https://github.com/user-attachments/assets/802df8aa-1203-4a4f-abbb-7ff42d8a978c" />

* VCC → 5V
* GND → GND
* TX → PA10 (USART1_RX)
* RX → PA9 (USART1_TX) (use voltage divider 1kΩ + 2kΩ to step 3.3V)

### Push Button (4-Pin)
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/a44e43d4-865e-4c31-8d1c-f8eb15ebd1c1" />

* One pin → PA0
* Opposite pin → GND
* Use internal pull-up in the STM32F411VET6.

### Green LED (Access Granted Indicator)
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/caee612a-e19a-4cb9-be8c-ff51c5f39f42" />

* Anode → PD12 through 220Ω resistor
* Cathode → GND

### Red LED (Door Closed / Access Denied Indicator)
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/39637c9d-16cf-4159-b33a-d75b5840a21a" />

* Anode → PD13 through 220Ω resistor
* Cathode → GND

### Buzzer
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/8134ce1e-4f9d-4f71-ba1b-dc5800523e53" />

* Positive → PD14
* Negative → GND

## Circuit Diagram 
![WhatsApp Image 2026-03-17 at 10 32 57 AM](https://github.com/user-attachments/assets/a459ae5a-f55a-4665-bb18-a08c71c57116)

## Issues Faced
* I had to interface all the hardware one at at time with the help of arduino,to check if all the hardware is working properly.
* I had to install serial bluetooth terminal app on phone.
* For bluetooth HC-05,stable wifif connection is needed otherwise the app doesnt show the message.
* Sometimes it has lose connections on the breadboard,so I suggest to connect all the hardware directly to the stm32f411vet 6 discovery board.
* After you get your final result,then only connect the oled and hc-05 to the breadboard.



## References
* https://www.st.com/resource/en/datasheet/stm32f411ve.pdf
* https://www.st.com/resource/en/reference_manual/dm00119316.pdf
* https://lastminuteengineers.com/hc05-at-commands-tutorial/
* https://learn.adafruit.com/monochrome-oled-breakouts.



