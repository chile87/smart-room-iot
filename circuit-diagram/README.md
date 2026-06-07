# Circuit Diagram (TinkerCAD-style SVG)

## How to view the SVG
- Open `/tmp/workspace/chile87/smart-room-iot/circuit-diagram/tinkercad-wiring-diagram.svg` directly in any modern browser.
- You can also embed it in Markdown via a relative link: `./tinkercad-wiring-diagram.svg`.
- Because the SVG uses a `viewBox`, it scales cleanly without quality loss.

## Component placement rationale
- **Arduino Uno R3** is centered at the top to minimize long crossing signal paths.
- **Breadboard 1 (left)** groups input and communication devices: DHT22, HC-SR04, LDR divider, HC-05.
- **Breadboard 2 (right)** groups output/display devices: Servo, LED+220Ω, Buzzer, LCD1602 I2C.
- This split mirrors subsystem boundaries and simplifies assembly/debugging.

## Color coding used
- **Red**: 5V / VCC distribution
- **Black**: GND return
- **Yellow**: Data signals (DHT22 data, HC-SR04 Echo, Servo signal, LCD SCL)
- **Orange**: HC-SR04 Trig
- **Green**: LDR analog, LED control, Bluetooth RX
- **Blue**: Bluetooth TX and LCD SDA (I2C/Serial class)
- **Purple**: Buzzer signal

## Connection verification checklist
- [ ] Arduino 5V connected to both breadboard positive rails
- [ ] Arduino GND connected to both breadboard negative rails
- [ ] DHT22: VCC/DATA/GND correctly mapped to rail+/D2/rail-
- [ ] HC-SR04: VCC/Trig/Echo/GND mapped to rail+/D3/D4/rail-
- [ ] LDR divider node connected to A0 with 10kΩ to GND
- [ ] HC-05: VCC/GND/TXD/RXD mapped to rail+/rail-/D10/D11
- [ ] Servo: Red/Brown/Yellow mapped to rail+/rail-/D9
- [ ] LED path is D5 → 220Ω → LED anode and cathode to GND
- [ ] Buzzer + on D6 and buzzer - on GND rail
- [ ] LCD I2C: VCC/GND/SDA/SCL mapped to rail+/rail-/A4/A5
- [ ] Common ground continuity confirmed for all components

## Bill of Materials (BOM)
- 1x Arduino Uno R3
- 2x Breadboard
- 1x DHT22 sensor
- 1x HC-SR04 ultrasonic sensor
- 1x LDR photoresistor
- 1x HC-05 Bluetooth module
- 1x SG90 servo motor
- 1x LED (single color)
- 1x Buzzer (active/passive)
- 1x LCD1602 with I2C backpack
- 1x 10kΩ resistor (LDR divider)
- 1x 220Ω resistor (LED current limiting)
- Assorted jumper wires
