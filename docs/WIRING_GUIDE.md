# Smart Room IoT Wiring Guide

## Safety warnings
1. Disconnect power before rewiring.
2. Verify rail polarity (+/-) before powering on.
3. Keep Arduino GND common with all module grounds.
4. Avoid shorting adjacent breadboard rows with bare leads.
5. For real hardware, protect HC-05 RXD with a voltage divider (Arduino TX is 5V logic).

## Step-by-step wiring

### 1) Place core hardware
- Place Arduino Uno at top-center.
- Place Breadboard 1 on the left (sensors/communication).
- Place Breadboard 2 on the right (actuators/display).

### 2) Power rails
- Arduino **5V → BB1 rail+** and **5V → BB2 rail+**.
- Arduino **GND → BB1 rail-** and **GND → BB2 rail-**.

### 3) Breadboard 1: sensors + communication
- **DHT22**
  - VCC → BB1 rail+
  - DATA → Arduino D2
  - GND → BB1 rail-
- **HC-SR04**
  - VCC → BB1 rail+
  - Trig → Arduino D3
  - Echo → Arduino D4
  - GND → BB1 rail-
- **LDR divider**
  - LDR pin1 → BB1 rail+
  - LDR pin2 → node (signal)
  - 10kΩ resistor from signal node → BB1 rail-
  - Signal node → Arduino A0
- **HC-05 Bluetooth**
  - VCC → BB1 rail+
  - GND → BB1 rail-
  - TXD → Arduino D10
  - RXD → Arduino D11

### 4) Breadboard 2: actuators + display
- **Servo SG90**
  - Red → BB2 rail+
  - Brown → BB2 rail-
  - Yellow → Arduino D9
- **LED + resistor**
  - Arduino D5 → 220Ω resistor → LED anode (+)
  - LED cathode (-) → BB2 rail-
- **Buzzer**
  - Buzzer + → Arduino D6
  - Buzzer - → BB2 rail-
- **LCD1602 I2C**
  - VCC → BB2 rail+
  - GND → BB2 rail-
  - SDA → Arduino A4
  - SCL → Arduino A5

## Troubleshooting tips
- **No sensor readings**: re-check DATA/Echo/Trig pins and common GND.
- **Servo jitter/reset**: power issue; use stronger 5V supply with shared GND.
- **LCD blank**: verify I2C address (often 0x27/0x3F) and contrast potentiometer.
- **Bluetooth unstable**: check baud rate and avoid noisy power lines.
- **LED not lighting**: verify anode/cathode orientation and resistor placement.

## Datasheet links
- Arduino Uno R3: https://docs.arduino.cc/hardware/uno-rev3
- DHT22: https://cdn.sparkfun.com/assets/f/7/d/9/c/DHT22.pdf
- HC-SR04: https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf
- HC-05: https://www.electronicaestudio.com/docs/istd016A.pdf
- SG90 Servo: https://components101.com/sites/default/files/component_datasheet/SG90%20Servo%20Motor%20Datasheet.pdf
- LCD1602 (HD44780 family): https://www.sparkfun.com/datasheets/LCD/HD44780.pdf
