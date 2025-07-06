# Wiring Diagram for Smart Grill/Oven Food Temperature Monitor

## Example for ESP32 with 4 Probes, OLED Display, Buzzer, and Button

```
+-------------------+         +-------------------+
|   Grill Probe 1   |---------| GPIO32 (ADC1_CH4) |
+-------------------+         +-------------------+
|   Grill Probe 2   |---------| GPIO33 (ADC1_CH5) |
+-------------------+         +-------------------+
|   Grill Probe 3   |---------| GPIO34 (ADC1_CH6) |
+-------------------+         +-------------------+
|   Grill Probe 4   |---------| GPIO35 (ADC1_CH7) |
+-------------------+         +-------------------+

Probes connect via 3.5mm audio jacks or thermocouple connectors. Use voltage divider or amplifier as needed for probe type.

+-------------------+
|   OLED Display    |
+-------------------+
| SDA ------------- GPIO21 (I2C SDA)
| SCL ------------- GPIO22 (I2C SCL)
| VCC ------------- 3.3V
| GND ------------- GND
+-------------------+

+-------------------+
|     Buzzer        |
+-------------------+
| +  -------------- GPIO25
| -  -------------- GND
+-------------------+

+-------------------+
|     Button        |
+-------------------+
| One side -------- GPIO26
| Other side ------ GND
+-------------------+

+-------------------+
|     ESP32         |
+-------------------+
| 5V/3.3V, GND, WiFi, BLE
+-------------------+

Power via USB or battery pack. Add battery monitor circuit if needed.
```

## Notes

- Use analog pins for thermistor probes, or appropriate amplifier for thermocouples (e.g., MAX31855 for Type K).
- Use I2C for display (SDA/SCL).
- Buzzer and button can use any available GPIO.
- For more than 4 probes, use analog multiplexers (e.g., CD4051) or I2C ADC expanders.

## What is a Voltage Divider? (for FireBoard and similar thermistor probes)

A voltage divider is an electronic circuit that allows the ESP32 to measure the resistance of a thermistor probe (like FireBoard probes) using an analog input pin. It consists of two resistors in series: one is the thermistor probe, and the other is a fixed resistor (reference resistor).

**Basic schematic:**

```
3.3V
 |
 |
[ R_fixed ]
 |
 |------> To ESP32 ADC pin (e.g., GPIO32)
 |
[ Thermistor Probe ]
 |
 |
GND
```

- **R_fixed**: A known, fixed resistor (e.g., 10kΩ or 100kΩ, chosen to match the thermistor's resistance at room temperature for best accuracy).
- **Thermistor Probe**: The FireBoard probe (NTC thermistor, e.g., 100kΩ at 25°C).
- The ESP32 analog pin reads the voltage at the junction between the two resistors. This voltage changes as the thermistor's resistance changes with temperature.

**How it works:**
- As the temperature changes, the resistance of the thermistor changes, which changes the voltage at the ADC pin.
- ESPHome uses this voltage (and the known value of R_fixed) to calculate the thermistor's resistance, and then the temperature.

**Choosing R_fixed:**
- For best accuracy, use a resistor value close to the thermistor's resistance at the temperature range you care about (e.g., 100kΩ for a 100kΩ probe at 25°C).
- Use a 1% tolerance resistor for best results.

**Summary:**
- The voltage divider is essential for reading thermistor probes with the ESP32.
- No special IC is needed—just a resistor and the probe.
- This method is used in the wiring diagram for each probe channel.

## Example: Wiring a FireBoard Probe with a 2.5mm Socket

```
3.3V
 |
 |
[ 100kΩ reference resistor ]
 |
 |-----------------------------+
 |                             |
 |                         [ ADC GPIO (e.g., GPIO32) on ESP32 ]
 |
 |                             |
 |                        +---------+
 |                        |         |
 |                        |         |
 |                  [2.5mm Socket]  |
 |                        |         |
 |                        |         |
 |                        +---------+
 |                             |
GND-----------------------------+
```

- **2.5mm Socket:**
  - Tip (or one terminal): Connect to the junction between the reference resistor and the ESP32 ADC pin.
  - Sleeve (or other terminal): Connect to GND.
- **Reference resistor (100kΩ, 1%):** Connects between 3.3V and the socket tip.
- The FireBoard probe plugs into the 2.5mm socket.
- The ESP32 reads the voltage at the junction (ADC pin) to determine the probe’s resistance and temperature.

**This setup allows you to easily swap probes and use standard FireBoard (or similar) probes with your project.**
