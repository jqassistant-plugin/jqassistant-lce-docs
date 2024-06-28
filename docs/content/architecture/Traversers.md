---
aliases:
  - traverser
---
# Traversers
-> traverse a given AST in a depth-first-search pattern and orchestrate the execution of [[Processors|processors]]

**Execution Steps:**
1. push a new empty map on the [[Local Contexts|local context stack]]
2. search the [[Feature Collections|feature collection]] for matching [[Processors|processors]] for the current [[Processing Context|processing context]] by evaluating their [[Execution Conditions|execution conditions]]
3. for all selected [[Processors|processors]]: run the pre-processing step
4. recursively start the traversal process for all AST child nodes of the current node and retrieve any extracted [[Language Concept|language concepts]] in the form of a [[Concept Map|concept map]]
5. for all selected [[Processors|processors]]: run the post-processing step and collect newly extracted [[Language Concept|concepts]] 
6. pop the current [[Local Contexts|local context map]]
7. apply [[Metadata Assignment Rules|metadata assignment rules]] to all newly extracted [[Language Concept|concepts]]
8. return the union of all extracted child [[Language Concept|concepts]] and all newly extracted [[Language Concept|concepts]] on this AST level

## Implementation
- visitor pattern for all scanned AST node types, which may either be self-implemented or provided by [[Native Tools and APIs|native APIs]] 
