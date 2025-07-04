# Smart Grill/Oven Food Temperature Monitor (ESPHome + Home Assistant)

This project is an open-source, WiFi-enabled grill/oven food temperature monitor designed for seamless integration with Home Assistant using ESPHome. It supports up to 4 temperature probes, an optional OLED display, buzzer, LED alerts, and more.

## Features

- Up to 4 temperature probes (thermistor or thermocouple)
- Optional SSD1306 OLED display with Home Assistant control
- Buzzer and LED alerts for over-temperature
- Battery voltage, WiFi signal, and device uptime monitoring
- Calibration offsets and alert thresholds per probe
- Fully local, no cloud required

## Hardware Requirements

See [BOM.md](./BOM.md) for a complete Bill of Materials.

- ESP32 Dev Board (recommended)
- Grill temperature probes (1-4)
- Probe connectors (3.5mm audio jack or thermocouple terminals)
- SSD1306 128x64 I2C OLED display (optional)
- Buzzer, LED, button (optional)
- Power supply (USB or battery)
- Enclosure (see [enclosure-suggestions.md](./enclosure-suggestions.md))

## Wiring

See [wiring-diagram.md](./wiring-diagram.md) for connection details.

## Firmware Setup

1. Install [ESPHome](https://esphome.io/guides/installing_esphome.html) on your computer.
2. Copy or customize `esphome-grill-monitor.yaml` for your hardware.
3. Edit secrets (WiFi, API, OTA passwords) and probe calibration as needed.
4. Flash the ESP32 using ESPHome:
   ```sh
   esphome run esphome-grill-monitor.yaml
   ```
5. Add the device to Home Assistant via the ESPHome integration.

## Calibration

- Follow [calibration-guide.md](./calibration-guide.md) to ensure accurate temperature readings.
- Set probe offsets and calibration points in Home Assistant or YAML.

## Home Assistant Integration

- All sensors, switches, and numbers are available as entities.
- Use the display, buzzer, and LED controls from Home Assistant.
- Create automations for notifications, logging, or advanced alerts.
- Example: Send a mobile notification if a probe exceeds its alert threshold.

## Customization

- Expand to more probes with analog multiplexers or I2C expanders.
- Add more display pages or custom graphics.
- Modify enclosure for your use case.

## Project Names

See [project-name-ideas.md](.github/project-name-ideas.md) for branding inspiration.

## Contributing

Pull requests and suggestions are welcome! See `.github/copilot-prompt.md` for project goals and best practices.

## License

MIT License. See [LICENSE](./LICENSE) if present.

---

> **Disclaimer:**
> This project is provided "as-is" without any warranty, guarantee of fitness for a particular purpose, or ongoing support. Use at your own risk. The authors and contributors are not responsible for any damages or issues arising from the use of this project.
