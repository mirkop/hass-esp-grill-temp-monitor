# Copilot Prompt for Smart Grill/Oven Food Temperature Monitor

This project is a smart grill/oven food temperature monitor designed to work locally with Home Assistant (HASS). It leverages ESPHome and off-the-shelf hardware to provide accurate, reliable, and extensible temperature monitoring for grilling, smoking, or oven cooking.

## Project Requirements

- Use components available from [ESPHome Components](https://esphome.io/components/)
- Identify supported microcontrollers from [ESPHome Supported Microcontrollers](https://esphome.io/components/#supported-microcontrollers)
- Use off-the-shelf grill temperature probes (e.g., from Amazon)
- Use an appropriate connector for the temperature probe (e.g., 3.5mm audio jack, thermocouple connectors)
- Support multiple temperature probes (document technical limits)
- Connect to HASS via WiFi; optionally support Zigbee, Z-Wave, BLE if feasible
- Define entities for temperature readings and calibration offset
- Add other useful entities (e.g., probe status, battery level, WiFi signal, alarm/alert thresholds, device uptime)
- Provide a Bill of Materials (BOM)
- Create an ESPHome YAML configuration
- Optionally support a display (OLED, LCD, or e-paper)
- Provide project name suggestions in `.github/project-name-ideas.md`

## Additional Suggestions

- Support for audible/visual alarms (buzzer, LED) when temperature thresholds are reached
- Expose device status (online/offline, last update)
- Option for OTA firmware updates
- Power options: USB, battery, or both (with battery monitoring)
- Enclosure recommendations (heat-resistant, weatherproof for outdoor use)
- Documentation for calibration procedure
- Optional support for logging temperature history to SD card or internal memory
- Security: recommend strong WiFi passwords, optionally support WPA3
- Accessibility: consider display contrast, font size, and colorblind-friendly indicators
- Easy reset/recovery procedure

---

This file is intended to guide Copilot and contributors in maintaining project focus and best practices.
