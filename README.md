# Live Air Raid Alert Map for Ukraine

A physical map displaying real-time data of any air raid alerts currently in effect in Ukraine. This project uses an ESP32 DevKit-C microcontroller unit with WS2812 addressable LEDs.

#### Main Objectives

- Gather and parse live alert data.
- Recovers automatically from network failures.
- Indicates current alert status by Ukrainian oblast.
- System is battery-powered and runs wirelessly.
- Supports OTA firmware updates

#### File Structure

```text
Live-Air-Raid-Map_UA/
├── README.md               #This file
├── docs/
│   ├── architecture.md     # Explains system architecture
│   ├── project-log.md      # A time log for any actions made during development
│   ├── requirements.md     # Outlines the requirements for the project
│   └── decisions/          # Contains files explaining the reasoning behind any decisions made during the project
│       ├── ADR-001_ESP32-Selected
│       ├── ADR-002_WS2812b-LED-Selected
│       ...
├── firmware/
│   └──
└──  hardware/
    └── 

```
  

