# Bluetooth-controlled-robot using STM32F407
This project presents the design and implementation of a **Bluetooth-controlled mobile robot** based on the **STM32F407 Discovery board**. The robot is remotely controlled via a **smartphone application** using Bluetooth communication, while simultaneously acquiring and transmitting **sensor data in real time**.
The project combines **embedded programming**, **hardware interfacing**, **interrupt management**, and **real-time communication**, making it a solid demonstration of applied embedded systems engineering.

---

## Project Overview
The robot communicates wirelessly with a smartphone through an **HC-06 Bluetooth module**. User commands (move forward, backward, turn left, turn right, stop) are sent from the mobile application to the STM32 microcontroller. In parallel, the system measures:
* Temperature using a **digital temperature sensor (DS1621)**
* Analog voltages from multiple ADC channels
All measured data are transmitted back to the smartphone and displayed in real time.

---

## System Architecture
The global system is organized around the STM32F407 microcontroller, which acts as the central controller :
* **STM32F407 Discovery**: Core processing unit
* **HC-06 Bluetooth module**: Wireless UART communication with smartphone
* **L298N motor driver**: Controls DC motors
* **DC motors + robot chassis**: Mechanical movement
* **DS1621 temperature sensor**: Digital temperature measurement (I2C)
* **ADC inputs**: Voltage measurements from multiple channels
* **Timers & External Interrupts**: Motor PWM control and event handling
A detailed block diagram of the architecture is provided in the repository.

---

## Hardware Components
* STM32F407 Discovery board
* HC-06 Bluetooth module
* L298N dual H-bridge motor driver
* 4-wheel robot chassis with DC motors
* DS1621 digital temperature sensor
* Breadboard and jumper wires
* External power supply / battery

---

## Software Features
* **Bluetooth communication (USART2)**
  * Bidirectional communication with smartphone
  * Reception of motion commands
  * Transmission of sensor data
* **Motor Control**
  * PWM generation using timers
  * Direction control via L298N
* **Sensor Acquisition**
  * Temperature reading via I2C (DS1621)
  * ADC readings from multiple channels
* **Interrupt Management**
  * External interrupts (user button)
  * Timer interrupts for periodic tasks
* **Real-Time Monitoring**
  * Live temperature and ADC values displayed on smartphone terminal

---

## Smartphone Interface
A Bluetooth terminal / custom control interface is used on the smartphone to:
* Send movement commands (AVANCE, RECULER, GAUCHE, DROIT, STOP)
* Display :
  * Temperature in °C
  * ADC channel values (CH1, CH2, CH3)
This provides intuitive and real-time interaction with the robot.

---

## Communication Protocol
* UART-based communication over Bluetooth
* Simple ASCII commands for robot control
* Periodic data frames for sensor transmission
This lightweight protocol ensures reliability and ease of debugging.

---

## Tools & Technologies
* **Microcontroller**: STM32F407
* **IDE**: Keil μ vision
* **Programming Language**: C
* **Communication**: UART, I2C
* **Debugging**: Serial terminal, live variable monitoring

---

## Learning Outcomes
Through this project, the following skills were developed:
* Embedded C programming on STM32
* Bluetooth communication and UART handling
* Real-time motor control using PWM
* Sensor interfacing (ADC & I2C)
* Interrupt-driven system design
* Integration of hardware and software into a complete embedded system
This project reflects a practical and scalable approach to **Bluetooth-based robotic control using STM32**, suitable for academic projects and embedded systems portfolios.
