---
aliases:
  - project
---
# Project
-> object containing all relevant metadata and extracted [[Language Concept|language concepts]] for a certain project that is scanned using the [[LCE Tool|LCE tool]]
- used to consolidate all information that is to be exported at the end of the [[Extractor API|extraction process]]

**Contains:**
- an object (usually of a type that is called something like `ProjectInfo`) that stores relevant metadata for the project
	- i.e. root path, config file location(s), references to other projects, ...
- a [[Concept Map|concept map]] containing all extracted language concepts for all source files of the project