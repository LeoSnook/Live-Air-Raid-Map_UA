# ADR 004: API Selected 

**Status:** Accepted
**Date:** 2026-07-09

---

### Context

The system requires a reliable source of live air raid alert data to display the current threat status of Ukrainian oblasts.

The selected API must:

- Provide current alert status data.
- Be accessible for personal projects.
- Provide sufficient geographical resolution to represent oblast-level status.
- Have documentation or predictable data formats suitable for embedded systems.

Three API sources were considered.

### Options Considered

#### Option 1: mapa.ua

Advantages:

- Publicly accessible without requiring approval.
- Provides threat positional data and alert information.
- Simple access method.

Disadvantages:

- Alert information differs from the official Ukraine Alarm map.
- The source and reliability of the displayed data is less suitable for this project.
- May provide more information than required for the initial project scope.

#### Option 2: api.ukrainealarm.com

Advantages:

- Official source of Ukrainian air raid alert data.
- Provides comprehensive regional alert information.
- Highest confidence in data origin.
- Designed specifically for applications requiring alert information.

Disadvantages:

- Requires developer registration and permission before use.
- Adds dependency on external approval before development can begin.


#### Option 3: raid.fly.dev

Advantages:

- Publicly accessible without requiring API approval.
- Provides data sourced from the Ukraine Alarm service.
- Provides sufficient information for the initial project requirement of displaying active alerts by oblast.
- Simple data structure suitable for use with an ESP32.

Disadvantages:

- Does not provide alert information for Crimea.
- Provides limited information compared with the official API.
- Does not provide detailed threat classifications.

### Decision

Option 3, raid.fly.dev, was selected as the initial API source.

The API provides sufficient functionality for the current project requirements while avoiding delays caused by requiring access approval. Since the primary objective of the first version is to display whether an oblast currently has an active alert, the additional information provided by the official API is not required.

The selected API also provides a simple data structure that is appropriate for an ESP32-based embedded system where processing resources are limited.

### Consequences

Positive:

- Development can begin immediately without waiting for API approval.
- The API provides sufficient information for the initial system design.
- Simple data structure reduces firmware complexity.
Reduces memory and processing requirements on the ESP32.

Negative:

- The system cannot currently display detailed threat information.
- Crimea cannot be represented using the current API.
- The project depends on a third-party API wrapper rather than the official API.
- Future changes to the API could require firmware modifications.

Future Considerations:

- Migration to the official Ukraine Alarm API may be considered later in development.
- Additional threat categories (such as missile or drone alerts) could be implemented if supported by a future data source.
- API reliability should be monitored during long-term operation.
- A fallback API source may be considered to improve system resilience.

### Related Requirements

- FR3
- FR4