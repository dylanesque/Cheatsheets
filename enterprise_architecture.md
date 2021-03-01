# Complexity

- Managing state is the single largest contributor to complexity in codebases.

- Flow of control and the volume of code also make significant contributions to complexity.

- Local complexity is addressed at the component level.

- "Can I know the result of this code at all times?" and "Can I reuse this code?" and "Can I test this code?"
  
- It is impossible to write good tests for bad code

- The Axis of Evil of Code:
  1) Hidden State
  2) Violating the SRP
  3) Nested Logic

- Possible fixes for hidden state include extracting to function parameters or methods, depending on the specifics of the hidden state

- Favor pure, immutable functions

- Abstractions should reduce complexity, and increase portability.

# OOP

- Think of objects as nouns

- Getting the domain model correct, esp in terms of accuracy, is the more important thing for a codebase.

- Modeling the domain as objects makes it easier to manage state later on

- Think of methods as verbs


