---
aliases:
  - native tools
---
# Native Tools and APIs
-> the [[index|LCE architecture]] strongly endorses the usage of tools and libraries that are native to the processed programming language

**Possible examples:**
- parsing or compiling libraries that provide access to the AST data structures for the individual source files
- language servers or similar tools that are able to perform type inference, dependency resolution, etc.
- other code processing or analysis tools or libraries

**Why use native tools?**
- native tools, especially first-party ones have (almost) always first-day support of new language features and are generally well maintained
- native APIs are usually specifically tailored towards the language at hand, allowing fine-grained access to syntactic and semantic constructs of the source code
- in many cases native tools and APIs have a performance lead on third-party solutions



