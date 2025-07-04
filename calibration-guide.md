# Calibration Guide for Smart Grill/Oven Food Temperature Monitor

Proper calibration ensures accurate temperature readings from your grill/oven probes. Follow these steps to calibrate each probe:

## 1. Prepare Calibration Equipment

- A reliable reference thermometer (digital kitchen thermometer or ice bath/boiling water method)
- Ice, water, and a pot for boiling water
- The assembled monitor with probes connected

## 2. Calibrate at Two Points (Recommended)

### Ice Water (0°C / 32°F)

1. Fill a glass with crushed ice and add cold water. Stir and let sit for 2 minutes.
2. Insert the probe and reference thermometer into the ice water, ensuring good contact.
3. Wait for readings to stabilize.
4. Note the temperature shown by the reference thermometer and the value reported by the ESPHome sensor in Home Assistant.
5. Record the difference (offset).

### Boiling Water (100°C / 212°F at sea level)

1. Bring a pot of water to a rolling boil.
2. Insert the probe and reference thermometer into the boiling water (do not touch the pot).
3. Wait for readings to stabilize.
4. Note the temperature shown by the reference thermometer and the value reported by the ESPHome sensor in Home Assistant.
5. Record the difference (offset).

## 3. Enter Calibration Offsets

- In Home Assistant, adjust the "Probe X Offset" number entity for each probe so the ESPHome reading matches the reference thermometer at both calibration points.
- If your probe is consistently off by the same amount, a single-point offset is sufficient. For more accuracy, use the NTC sensor's calibration points in the ESPHome YAML for multi-point calibration.

## 4. Multi-Point Calibration (Advanced)

- Edit the `calibration:` section for each probe in `esphome-grill-monitor.yaml`.
- Add calibration pairs as follows:
  ```yaml
  calibration:
    - [0, 10000] # [temperature °C, resistance Ohms]
    - [100, 1000]
  ```
- Use resistance values from your probe's datasheet or measure with a multimeter at known temperatures.

## 5. Save and Test

- Save changes and upload the configuration to your device.
- Verify readings at room temperature, ice water, and boiling water.
- Repeat as needed for all probes.

## Tips

- Calibrate regularly, especially if you change probes.
- Use the same method for all probes for consistency.
- Document your calibration values for future reference.
