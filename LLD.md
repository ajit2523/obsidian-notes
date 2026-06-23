### [[Classes & Objects]]
- **What are the key classes?**
- **What are their responsibilities?**
- **What data do they hold (attributes)?**
- **What operations do they perform (methods)?**
### [[Interfaces & Abstractions]]
- Interface defines contracts between components
- critical to ensure **loose coupling,** allowing multiple components to interact without depending on each other's internal implementation details.
### Relationship between Classes
-  **Association:** A general "uses-a" relationship. A `Doctor` _uses a_ `Stethoscope`.
- **Aggregation (Weak "has-a"):** An object contains other objects, but they can exist independently.
- **Composition (Strong "has-a"):** An object is _composed of_ other objects, and their lifecycles are tied.
- **Inheritance ("is-a"):** A class inherits properties and behaviors from a parent.
### Cardinality
**the number of instances** involved in a relationship.
- **One-to-One:** One instance of A is linked to one instance of B.
- **One-to-Many:** One instance of A is linked to multiple instances of B.
- **Many-to-Many:** Multiple instances of A relate to multiple instances of B.
### Design Patterns
- **Singleton:** useful when you need exactly one instance of a class across your system.
- **Factory:** useful when you want to delegate object creation without exposing the instantiation details to the client.
- **Strategy:** useful when you need to switch between multiple algorithms or behaviors at runtime.
- **Observer:** useful for event-driven systems where you need to establish a publisher–subscriber relationship between objects.
- **Decorator:** useful when you want to add new behavior to objects without altering existing code.
- **Adapter:** useful when you need to bridge incompatible interfaces to work together.
- **Facade:** useful when you want to provide a simplified interface to a complex subsystem.