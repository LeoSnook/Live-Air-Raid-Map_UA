# Requirements

This document outlines the requirements this project must meet to be considered complete.

---

### Functional Requirements

**FR1:** The controller must automatically connect to WiFi upon activation.
Conditions of satisfaction:
1. Upon bootup, the controller must attempt to establish a WiFi connection.
2. If a connection cannot be made, the controller must reattempt to establish a connection after 15 seconds.

**FR2:** The controller must automatically be able to handle disrupted WiFi connections.
Conditions of satisfaction:
1. The loss of internet access must be indicated to the user through the use of an LED.
2. The controller must repeatedly attempt to re-establish an internet connection.

**FR3:** The controller must use LEDs to indicate the status of an air raid in a particular oblast.
Conditions of satisfaction:
1. One LED represents the air raid status of an entire oblast.
2. A red colour must be used to indicate threats.

**FR4:** The controller must retrieve current air raid data from a trusted online source.
Conditions of satisfaction:
1. Air raid data must be obtained from a trustworthy API.
2. Air raid data must be refreshed every 60 seconds

**FR5:** The controller must support firmware updates
Conditions of satisfaction:
1. Firmware updates must be installable via USB-C
2. Firmware updates must also be installable wirelessly.

**FR6:** The controller must handle failures when retrieving data.
Conditions of satisfaction:
1. Failure to retrieve data must be handled without restarting the system.
2. The user must be informed if any data becomes unavailable.
3. Any regions affected by unavailable data should be identified as such.

**FR7**: The system architecture should allow replacement of the air raid data provider without significant firmware changes.


---

### Non-Functional Requirements

**NFR1:** Startup time must take less than 15 seconds.

**NFR2:** The system must operate continuously without user intervention following initial configuration.

---

### Physical Design Requirements

**PDR1:** The purpose of each LED must be clearly indicated.
Conditions of satisfaction:
1. The oblast each LED represents must be labelled
2. Each oblast LED position must correspond to that oblast.
3. The purpose of any other status LEDs must be labelled.
4. Labels must be visible during operation.

**PDR2:** The device must resemble the map of Ukraine, with oblast borders clearly shown.

---

### Design Constraints

**DC1:** The controller must be based on a general purpose microcontroller

**DC2:** The controller must use LEDs to communicate with the user.

**DC3:** The system must use WiFi as its primary data retrieval method.

**DC4:** The system must have the capability to be powered by both battery or USB.

**DC5:** The map must represent all Ukrainian oblasts.