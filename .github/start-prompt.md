I want to create a smart grill/oven food temperature monitor that will work locally with Home Assistant (HASS).

Add a `.github/copilot-prompt.md` file and initialize it for this project.
Configure files and folders as needed for this project.

Here as some requiremets that I have thought of. Please add more ideas that you might have to make this work and to make it even better. Let me know if i have missed anything and add that.

- use components available from https://esphome.io/components/
- identify which supported microcontrollers would work for this project: https://esphome.io/components/#supported-microcontrollers
- use off-the-shelf grill temperature probes (amazon.com).
- use an appropriate connector for the temp probe
- provide an option to add multiple temp probes. Indicate how many are technically possible.
- It should connect to HASS via WiFi and other optional wireless transports (zigbee, zwave, ble) if it technically make sense.
- define entities for the temperature, and an offset for calibration.
- add any other entities that may be useful or important to have
- provide a BOM in a file somewhere.
- create a esphome yaml configuration: https://esphome.io/guides/yaml
- provide an option for a display if technically possible.
- provide some suggestions for names for this project. put them in a file called `.github/project-name-ideas.md`

save this prompt to a file called `.github/start-prompt.md`. tell me how i could have improved this prompt by adding a NOTES: section at the bottom of that file. I'm working on improving my prompt skills.

---

NOTES:

- You could improve this prompt by adding a **NOTES:** section at the bottom, where you clarify any special constraints, preferences, or context (e.g., preferred microcontroller, display type, enclosure requirements, power source, or integration details with HASS). This helps Copilot and contributors better understand your goals and avoid ambiguity.
- Consider specifying your technical skill level or preferred documentation style if relevant.
- If you have a timeline or milestones, mention them here.
