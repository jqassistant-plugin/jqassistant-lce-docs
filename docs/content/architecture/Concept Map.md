---
aliases:
  - concept map
---
# Concept Map
-> data structure to handle sets of [[Language Concept|language concept]] objects
- maps [[Language Concept|language concept]] type IDs to lists of [[Language Concept|language concept]] objects of that type
	- optionally, additional information about where in the AST certain [[Language Concept|language concept]] objects were extracted can be used as key as well
- used by [[Traversers|traversers]], [[Processors|processors]], and [[Post Processors|post processors]] to pass around [[Language Concept|language concept]] data
- central data structure contained within a [[Project|project]] object

## Implementation
**Two possible structures:**
- `Map<String, Concept[]>`: maps [[Language Concept|language concept]] type ID to a list containing all [[Language Concept|language concepts]] of that type extracted so far
	- recommended, as it is easier to handle than the version below
- `Map<String, Map<String, Concept[]>>`: maps the identifier of the child AST node under which a number of [[Language Concept|language concept]] were extracted to an instance of the data structure described above
	- this is useful when trying to discern between multiple extracted [[Language Concept|concepts]] of the same type, but in different contexts
	- e.g. `class MyClass extends BaseType implements SomeOtherType`, may lead to two type reference [[Language Concept|concept]] objects being extracted. To compose them (along with other concepts) to a class declaration they need to be differentiated via the first map key.
	- this structure isn't strictly needed and can be avoided by using [[Local Contexts|local contexts]] for providing a partially initialized parent [[Language Concept|concept]] object to [[Processors|processors]] further down the tree