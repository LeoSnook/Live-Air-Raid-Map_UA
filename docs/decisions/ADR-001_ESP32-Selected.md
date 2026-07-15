# ADR 001: ESP32 Selected

**Status:** Accepted
**Date:** 2026-06-27

---

### Context

The system requires a widely available microcontroller capable of connecting to the internet to retrieve live air raid data. The chosen platform must support WiFi communication, provide sufficient processing capability to handle network communication and LED control, and be widely accessible for good documentation and development tool support.

Several candidate platforms were considered, each with different strengths and weaknesses.

### Options Considered

#### Option 1: STM32 MCUs

Advantages:

- Widely used in industry and embedded systems.
- Excellent performance and low power consumption.
- Strong professional development ecosystem.

Disadvantages:

- Most development boards do not include built-in WiFi.
- Additional hardware would be required to obtain internet connectivity.
- More complex setup compared to integrated WiFi solutions.
- Increased project cost and hardware complexity.

#### Option 2: ESP32 MCUs

Advantages:

- Integrated WiFi and Bluetooth connectivity.
- Most boards are low cost and widely available.
- Extensive online documentation and community support.
- Compatible with Arduino IDE, PlatformIO, and ESP-IDF.
- Sufficient processing power and memory options for the project's requirements.
- Supports over-the-air firmware updates.

Disadvantages:

- Higher power consumption than some STM32 devices.
- Less common in safety-critical or industrial applications.
- WiFi functionality introduces additional firmware complexity.

#### Option 3: Raspberry Pi

Advantages:

- Integrated WiFi and Bluetooth connectivity.
- Significantly greater processing power and memory.
- Capable of running a full Linux operating system.
- Large software ecosystem.

Disadvantages:

- Significantly more expensive than a microcontroller solution.
- Longer boot times.
- Higher power consumption.
- Computational capabilities greatly exceed project requirements.
- Introduces unnecessary system complexity for a primarily embedded application.

### Decision

Option 2, specifically the ESP32-WROOM-32D DevKitC, was selected as the controller.

The ESP32 provides integrated WiFi connectivity, allowing direct access to online air raid alert APIs without requiring additional networking hardware. Bluetooth functionality also enables future implementation of wireless firmware updates and device configuration.

The platform offers a favourable balance between cost, capability, ease of development, and community support. Its extensive documentation and compatibility with multiple development environments reduce development risk and make the project easier to maintain and extend.

Furthermore, the ESP32's processing power and memory resources are sufficient for handling network communication, JSON parsing, LED control, and future feature expansion while remaining significantly less complex than a single-board computer solution such as the Raspberry Pi.

### Consequences

Positive:

- Integrated WiFi simplifies hardware design.
- Integrated Bluetooth enables future wireless update functionality.
- Low component cost.
- Large community and extensive learning resources.
- Rapid development using familiar toolchains.
- Sufficient performance for current and anticipated system requirements.

Negative:

- Greater power consumption than some STM32 alternatives.
- Reliance on WiFi increases system dependence on network availability.
- Platform is less representative of some industrial embedded environments.

Future Considerations:

- Migration to ESP-IDF may be beneficial if the firmware becomes significantly more complex.
- Future hardware revisions may evaluate alternative ESP32 variants with improved power efficiency.
- If industrial deployment is ever required, an STM32-based design could be reconsidered.

### Related Requirements

- FR1
- FR2
- FR4
- FR5
- DC1
- DC4