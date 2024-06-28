---
aliases:
  - feature collections
---
# Feature Collections
-> global data structures that contain instances of all available [[Traversers|traversers]], [[Processors|processors]], and/or [[Post Processors|post processors]]
- used by  [[Extractor API|extractor API]] and [[Traversers|traversers]] to find eligible processing candidates
- can be used to build [[Extensions|extensions]]

## Implementation
- for [[Processors|processors]] and [[Post Processors|post processors]] simple lists of their abstract super type can be used
- for [[Traversers|traversers]] a map that maps AST node types to the respective traverser implementation may be used