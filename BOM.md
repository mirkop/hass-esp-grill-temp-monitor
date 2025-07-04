# Bill of Materials (BOM) for Smart Grill/Oven Food Temperature Monitor

| Item                            | Example/Notes                                  | Quantity  | Source/Link                                                               |
| ------------------------------- | ---------------------------------------------- | --------- | ------------------------------------------------------------------------- |
| ESP32 Dev Board                 | ESP32-WROOM-32, ESP32-S3, ESP32-C3 recommended | 1         | [ESPHome MCUs](https://esphome.io/components/#supported-microcontrollers) |
| Grill Temperature Probe         | Thermistor or thermocouple (Type K)            | 1-4       | Amazon, eBay                                                              |
| Probe Connector                 | 3.5mm audio jack, thermocouple connector       | 1-4       | Amazon, AliExpress                                                        |
| OLED Display (optional)         | SSD1306 128x64 I2C                             | 1         | Amazon, AliExpress                                                        |
| Buzzer (optional)               | Piezo or active buzzer                         | 1         | Amazon, AliExpress                                                        |
| LED (optional)                  | Indicator for status/alerts                    | 1-2       | Any electronics supplier                                                  |
| Button (optional)               | For reset or calibration                       | 1         | Any electronics supplier                                                  |
| Power Supply                    | USB 5V adapter or battery pack                 | 1         | Any electronics supplier                                                  |
| Enclosure                       | Heat-resistant, weatherproof recommended       | 1         | Amazon, 3D print, custom                                                  |
| Wires, headers, resistors, etc. | For assembly and connections                   | as needed | Any electronics supplier                                                  |

## Notes

- ESP32 is recommended for WiFi and BLE support. Zigbee/Z-Wave require additional modules and are not natively supported by ESPHome.
- Number of probes depends on available analog/digital pins. ESP32 can support 4+ with multiplexing or I2C expanders.
- Choose probe and connector types that match (thermistor or thermocouple).
- Display, buzzer, LED, and button are optional but recommended for usability.
- Enclosure should be food-safe and heat-resistant if used near grills/ovens.
