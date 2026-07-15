# ADR 003: VSCode IDE Selected

**Status:** Accepted
**Date:** 2026-07-07

---

### Context

The project requires a development environment capable of supporting firmware development, version control, documentation authoring, and future project expansion.

The chosen environment should provide a streamlined workflow and integrate well with modern software development practices. It should also support the ESP32 platform and be accessible to future contributors.

### Options Considered

#### Option 1: VSCode

Advantages:

- Supports a wide range of programming languages and file types.
- Integrates directly with Git and GitHub.
- Compatible with PlatformIO and Arduino development workflows.
- Extensive extension ecosystem.
- Supports Markdown authoring for project documentation.
- Advanced code navigation, refactoring, and debugging features.
- Widely used in industry.

Disadvantages:

- More complex initial setup.
- Greater resource usage than Arduino IDE.
- Larger learning curve for beginners.

#### Option 2: Arduino IDE

Advantages:

- Simple installation and configuration.
- Beginner-friendly interface.
- Direct support for ESP32 development.
- Large number of tutorials and examples available.

Disadvantages:

- Limited project management capabilities.
- Basic code navigation and editing features.
- Limited integration with professional development workflows.
- Less suitable for larger, multi-file projects.
- Documentation and firmware development occur in separate environments.

### Decision

Option 1, Visual Studio Code, was selected as the primary development environment.

Visual Studio Code provides a unified workspace for firmware development, documentation, version control, and project management. Its integration with Git and GitHub supports the project's goal of maintaining a professional development workflow and in-depth project history.

The ability to use extensions such as PlatformIO also provides a more scalable development environment should the firmware become more complex over time.

### Consequences

Positive:

- Improved productivity through advanced editing and navigation tools.
- Integrated Git and GitHub workflows.
- Support for multi-file project structures.
- Simplified management of project documentation.
- Easier adoption of professional software engineering practices.
- Flexible environment for future project expansion.

Negative:

- Increased setup complexity compared to Arduino IDE.
- Additional learning required to configure and use extensions.
- Potential compatibility issues between extensions and toolchains.

Future Considerations:

- Automated formatting tools may be introduced.

### Related Requirements

- Overall project