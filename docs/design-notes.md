# Design Notes


### Component Selection
- MCU = ATMEGA328PB-AU
  - worked with MCU before
  - cheap
  - I2C capabilities for sensor communication
  - UART abilities
  - AU = 32 pins = easier to solder by hand
 <img width="2000" alt="image" src="https://github.com/user-attachments/assets/663ca82e-a8a7-4b3d-aa3d-98e9aced5e7f" />
  - ISP header
  - reset resistor
  - 2 capacitors

 
- Sensor= BME280
  - measures temp, humidity, pressure
  - popular
  - I2C, therefore can communicate with ATmega328PB
 <img width="2000" alt="image" src="https://github.com/user-attachments/assets/57ff7a1b-304c-4a1f-87f5-3824d1a44553" />
 <img width="2000" alt="Sensor wiring I2C" src="images/sensor_wiring.png" />
  - NOTE: a direct connection between CSB and Vddio required
  - 2 capacitors
  - 2 pull up resistors


- Regulator = MIC5504-3.3YM5-TR
  - 3.3V LDO
  - SOT23-5 (easier for soldering)
  - 300 mA
  - cheap
<img width="2000" alt="image" src="https://github.com/user-attachments/assets/37e2a8ea-d332-4f3f-a267-875c7cbbf943" />
<img width="2000" alt="Typical regulator application" src="images/typical_app_regulator.png" />
  - 2 capacitors 




   
- 2 LEDS
  - D1 for power
    - Green LED
    <img width="2000" alt="Green LED Digikey" src="images/GREENLED.png" />
    - close to the regulator output (3.3 V rail), not directly on USB 5 V to ensure that regulator is working and correctly supplying a 3.3 V rail

  - D2 for status/heartbeat
    - Red LED
    <img width="2000" alt="Red LED Digikey" src="images/REDLED.png" />

  - 1k resistors for both LEDs
    <img width="2000" alt="Red LED Digikey" src="images/1KRESISTOR.png" />
    - allows for enough current for visibility, but saves power
    - 3.3 V supply after regulator, drops 2 V across LED, leaves 1.3 V for resistor
    - desired current above 1mA for visibility, 1.3 mA for nice number and easier visibility
    - Ohm's Law: R = V/I = 1.3/1.3 mA = 1k resistor


  - 2 4.7 k pull up resisotrs for the BME280 sensor
    - as stated in datasheet (normal value)
    <img width="2000" alt="Red LED Digikey" src="images/4.7_resistor_surface.png" />

  - 2 100 nF capacitors for the BME280 sensor
  <img width="2000" alt="Red LED Digikey" src="images/100nF_capacitor.png" />

  - ISP header for programming with ATMEGA (MISO, MOSI, SCK, RESET, 3.3 V, GND)
  <img width="2000" alt="Red LED Digikey" src="images/ISP_header_6.png" />

  - 10 k reset resistor for ATMEGA
  <img width="2000" alt="Red LED Digikey" src="images/10k_resistor_SM.png" />

  - 2 100 nF capacitors for ATMEGA
  <img width="2000" alt="Red LED Digikey" src="images/100nF_capacitor.png" />

    

