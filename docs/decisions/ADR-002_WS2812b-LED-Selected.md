# ADR 002: WS2812B LED Selected

**Status:** Accepted
**Date:** 2026-06-27

---

### Context

The system requires one LED to represent the air raid status of each Ukrainian oblast. Each indicator must be individually controllable to allow different regions to display different threat states simultaneously.

The selected solution should minimise wiring complexity, reduce the number of required microcontroller I/O pins, and simplify future expansion of the system.

Several LED technologies were considered.

### Options Considered

#### Option 1: Discrete LEDs

Advantages:

- Low component cost.
- Simple operating principle.
- Widely available.
- Available in a variety of colours.

Disadvantages:

- Requires a dedicated GPIO pin or additional driver circuitry for each LED.
- Significantly increases wiring complexity.
- More difficult to assemble and troubleshoot.
- Limited ability to support additional status colours without using RGB LEDs and further increasing complexity.
- Expansion would require additional hardware resources.

#### Option 2: WS2812 LED strips

Advantages:

- Individually addressable LEDs.
- Multiple LEDs can be controlled using a single microcontroller pin.
- Full RGB colour control enables future expansion of threat states.
- Widely used and well supported by existing software libraries.
- Simplified wiring compared to discrete LEDs.

Disadvantages:

- LEDs are fixed at regular spacing.
- Strip format may not align naturally with the physical layout of Ukrainian oblasts.
- Excess LEDs may be wasted during construction.
- Physical integration into the map may require modification of the strip.

#### Option 3: 5mm WS2812b LED modules

Advantages:

- Individually addressable RGB LEDs.
- Single data line can control all LEDs.
- Greater flexibility when positioning LEDs on the map.
- Simplified wiring compared to discrete LEDs.
- Full RGB colour support allows future addition of new alert states.
- Easier to align with the geographical layout of oblasts.

Disadvantages:

- Higher cost per LED than strip-based solutions.
- Slightly larger physical footprint.
- More soldering may be required during assembly.

### Decision

Option 3, 5mm WS2812B LED modules, was selected.

The project requires LEDs to be positioned according to the geographical locations of Ukrainian oblasts. While WS2812B strips provide the necessary addressable RGB functionality, their fixed spacing makes them less suitable for representing an irregular geographic layout.

The 5mm WS2812B modules provide the same addressable RGB functionality while allowing each LED to be placed independently. This significantly simplifies the physical design of the map and enables a more accurate representation of oblast locations.

The ability to control all LEDs from a single data pin also reduces wiring complexity and preserves GPIO resources on the ESP32 for potential future features.

### Consequences

Positive:

- Only a single microcontroller data pin is required to control all LEDs.
- Reduced wiring complexity compared to discrete LEDs.
- Flexible LED placement enables accurate map representation.
- RGB colour support allows future expansion of alert states.
- Large ecosystem of existing software libraries and examples.

Negative:

- Higher component cost than standard discrete LEDs.
- Requires use of a specialised communication protocol.
- Increased power consumption compared to a single-colour LED solution.
- Additional consideration must be given to power distribution if brightness is increased.

Future Considerations:

- Additional threat categories may be represented using alternative colours.
- Brightness control may be implemented for user accessibility.
- If LED count increases significantly, dedicated power injection points may be required.

### Related Requirements

- FR3
- DC2