# Circuit Diagram (TinkerCAD Realistic SVG)

## Main diagram
- Primary SVG: [`circuit-diagram/tinkercad-realistic-wiring.svg`](./tinkercad-realistic-wiring.svg)
- Legacy SVG (kept for compatibility): [`circuit-diagram/tinkercad-wiring-diagram.svg`](./tinkercad-wiring-diagram.svg)

## How to view
1. Open `circuit-diagram/tinkercad-realistic-wiring.svg` in any browser.
2. Zoom in to inspect breadboard holes, rails, and pin-level routing.
3. Cross-check each wire against `connections-table.md`.

## Component placement guide
- **Top breadboard**: DHT22 (left), LDR+10kΩ (center-left), HC-SR04 (right), HC-05 module (center-right).
- **Center**: Arduino Uno R3.
- **Bottom breadboard**: LCD1602 I2C (left), LED+220Ω (center-left), Micro Servo (center-right), Piezzo Buzzer (right).

## Wire color legend
- **Red**: 5V / VCC power
- **Black**: GND return
- **Yellow**: DHT22 data, HC-SR04 Echo, Servo signal
- **Orange**: HC-SR04 Trig and buzzer positive line
- **Green**: LDR analog node (A0) and LED control path
- **Blue**: LCD SDA (A4)
- **Light Blue**: LCD SCL (A5)

## Connection checklist
- [ ] Top and bottom breadboards have clear + (red rail) and - (blue rail) power rails
- [ ] Arduino 5V and GND fan out to both breadboards
- [ ] DHT22 is wired VCC / DATA / GND to rail+ / D2 / rail-
- [ ] LDR divider is wired to A0 with 10kΩ to ground
- [ ] HC-SR04 is wired VCC / Trig / Echo / GND to rail+ / D3 / D4 / rail-
- [ ] LCD1602 I2C is wired VCC / GND / SDA / SCL to rail+ / rail- / A4 / A5
- [ ] LED is wired through 220Ω to D5 and cathode to GND
- [ ] Servo is wired Red / Brown / Yellow to rail+ / rail- / D9
- [ ] Buzzer + is wired to D6 and buzzer - to GND rail

## Notes
- Bluetooth HC-05 is included on the top breadboard for architecture completeness.
- The SVG uses a 1600×1200 viewBox and grouped layers (`top-breadboard`, `arduino-uno`, `bottom-breadboard`, `wiring`, `labels`) for easy editing.
