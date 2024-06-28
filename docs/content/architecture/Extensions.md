---
aliases:
  - extensions
---
# Extensions
-> optional parts of the [[LCE Tool|LCE tool]] that provide additional [[Traversers|traversers]], [[Processors|processors]], and/or [[Post Processors|post processors]] to extend the extraction capabilities
- can be used to provide framework-specific extraction capabilities

## Implementation
- extensions could be enabled via specific CLI flags or other configuration mechanisms
- if enabled an initialization function adds the required [[Traversers|traversers]], [[Processors|processors]], and/or [[Post Processors|post processors]] instances to the respective [[Feature Collections|feature collections]]