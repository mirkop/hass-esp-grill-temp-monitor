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
