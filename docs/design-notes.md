# Design Notes


### Component Selection
- MCU = ATMEGA328PB-AU
  - worked with MCU before
  - cheap
  - I2C capabilities for sensor communication
  - UART abilities
  - AU = 32 pins = easier to solder by hand
 <img width="2000" alt="image" src="https://github.com/user-attachments/assets/663ca82e-a8a7-4b3d-aa3d-98e9aced5e7f" />

 
- Sensor= BME280
  - measures temp, humidity, pressure
  - popular
  - I2C, therefore can communicate with ATmega328PB
 <img width="2000" alt="image" src="https://github.com/user-attachments/assets/57ff7a1b-304c-4a1f-87f5-3824d1a44553" />


- Regulator = MIC5504-3.3YM5-TR
  - 3.3V LDO
  - SOT23-5 (easier for soldering)
  - 300 mA
  - cheap
<img width="2000" alt="image" src="https://github.com/user-attachments/assets/37e2a8ea-d332-4f3f-a267-875c7cbbf943" />



   
- 2 LEDS
  - D1 for power
    - Green LED
    <img width="2000" alt="Green LED Digikey" src="GREENLED.png" />
    - close to the regulator output (3.3 V rail), not directly on USB 5 V to ensure that regulator is working and correctly supplying a 3.3 V rail

  - D2 for status/heartbeat
    - Red LED
    <img width="2000" alt="Red LED Digikey" src="REDLED.png" />

  - 1k resistors for both LEDs
    <img width="2000" alt="Red LED Digikey" src="1KRESISTOR.png" />
    - allows for enough current for visibility, but saves power
    - 3.3 V supply after regulator, drops 2 V across LED, leaves 1.3 V for resistor
    - desired current above 1mA for visibility, 1.3 mA for nice number and easier visibility
    - Ohm's Law: R = V/I = 1.3/1.3 mA = 1k resistor




