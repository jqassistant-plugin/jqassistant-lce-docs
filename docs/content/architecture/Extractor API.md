---
aliases:
  - extractor API
---
# Extractor API
-> central API of the [[LCE Tool|LCE tool]] that orchestrates the language concept extraction and export process
- controlled by the user via CLI calls of the tool

**Central Function:** Detect and scan all projects that are located within a provided scan directory and export the extracted information to a JSON file

**Steps:**
1. locating any source projects contained within the provided scan path
2. determining any metadata needed for further processing (e.g. references to other projects, locations of important config files, etc.)
3. initializing any required [[Native Tools and APIs|native tools/APIs]]
4. executing the [[Traversers|traverser]] for the individual source files to extract the [[Language Concept|language concepts]] from the code
5. bundling the extracted [[Language Concept|concepts]] and the acquired project metadata into [[Project|project]] objects
6. executing the [[Post Processors|post processors]] on the [[Project|project]] objects
7. exporting the [[Project|project]] objects to a JSON file

## Implementation
- depends on the used CLI library
- simplest case: just a collection of static functions called by a `main` method or similar