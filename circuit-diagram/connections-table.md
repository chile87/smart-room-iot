# Smart Room IoT Wiring Connections Table

| # | From | To | Wire Color |
|---|------|----|------------|
| 1 | Arduino 5V | Top breadboard rail + | Red |
| 2 | Arduino GND | Top breadboard rail - | Black |
| 3 | DHT22 VCC | Top breadboard rail + | Red |
| 4 | DHT22 DATA | Arduino D2 | Yellow |
| 5 | DHT22 GND | Top breadboard rail - | Black |
| 6 | HC-SR04 VCC | Top breadboard rail + | Red |
| 7 | HC-SR04 Trig | Arduino D3 | Orange |
| 8 | HC-SR04 Echo | Arduino D4 | Yellow |
| 9 | HC-SR04 GND | Top breadboard rail - | Black |
| 10 | LDR top leg | Top breadboard rail + | Red |
| 11 | LDR divider node | Arduino A0 | Green |
| 12 | 10kΩ resistor lower leg | Top breadboard rail - | Black |
| 13 | Arduino 5V | Bottom breadboard rail + | Red |
| 14 | Arduino GND | Bottom breadboard rail - | Black |
| 15 | LCD VCC | Bottom breadboard rail + | Red |
| 16 | LCD GND | Bottom breadboard rail - | Black |
| 17 | LCD SDA | Arduino A4 | Blue |
| 18 | LCD SCL | Arduino A5 | Light Blue |
| 19 | LED anode path (through 220Ω) | Arduino D5 | Green |
| 20 | LED cathode | Bottom breadboard rail - | Black |
| 21 | Servo RED | Bottom breadboard rail + | Red |
| 22 | Servo BROWN | Bottom breadboard rail - | Black |
| 23 | Servo YELLOW | Arduino D9 | Yellow |
| 24 | Buzzer + | Arduino D6 | Orange |
| 25 | Buzzer - | Bottom breadboard rail - | Black |

## Breadboard / module notes
- Top board includes DHT22, LDR+10kΩ, HC-SR04, and HC-05.
- Bottom board includes LCD1602 (I2C), LED+220Ω, Micro Servo, and Piezzo Buzzer.
- All grounds are common and tied back to Arduino GND.
