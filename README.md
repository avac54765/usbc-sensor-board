# Creating a USB-C Environmental Monitor

Personal project to gain further experience in PCB design, power electronics, and embedded systems. 

## Project Goals
- Gain further experience in KiCad
- Design a two-layer PCB
- Practice choosing components and verifying behavior in LTSpice
- Further gain experience in embedded hardware design

## Tools
- KiCad
- LTspice
- GitHub



## PURPOSE:
Design a PCB to measure the current temperature, pressure, and humidity of the environment, powered with a USB-C input. 
This board will:
1. Be powered by USB-C (5V)
2. regulate power to 3.3 V
3. Use the ATmega328PB microcontroller
4. Use a sensor to read current environmental data
5. LED for power status
6. Heartbeat LED for status and debugging
7. Transmit sensor data via UART to PC for viewing data


### Component Selection
- MCU = ATmega328PB
  - worked with MCU before
  - cheap
  - I2C capabilities for sensor communication
  - UART abilities
 
- Sensor= BME280
  - measures temp, humidity, pressure
  - popular
  - I2C, therefore can communicate with ATmega328PB

  - Regulator = AP2112K-3.3
    - 3.3V LDO
   
  - 2 LEDS
    - D1 for power
    - D2 for status/heartbeat

