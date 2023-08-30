# Design Pattern


# Classification of Design Patterns
There are different types of design pattern. These are differed from each other on the basis of complexity, details level, intent and scale of applicability to the entire system being design. Design Patterns are mainly classified into three categories. Such as:

1. Creational Design Pattern: It provides mechanism to create objects without revealing the creation method that enhance the flexibilities and reusability of the existing code. Example: Factory, Builder, etc.
2. Structural Design Pattern: It is about class-object composition i.e. classes combined together to form a bigger structure for achieving multiple goals altogether. Example: Decorator, Facade, etc.
3. Behavioral Design Pattern: This pattern type is concerned with the communication between objects and the assignment of responsibilities between objects, or, encapsulating behavior in an object and delegating requests to it. Example: Observer, Strategy, etc.

## Factory Pattern
- It encapsulates object creation logic.
- Defines an interface for creating an object, but let subclass decide which class to instantiate.
- Factory method depends on inheritance.
- All factory patterns promote loose coupling.
- The Factory Pattern helps us to align with the Dependency Inversion principle.
  ### Main Components
  
  <img src="[https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/981b47c1-0ae6-4c11-ac8b-d4ef427744b9" width=50% height=30%>

  **Creator:** can be an abstract class or concrete class which should define the factory method.
  **Concrete Creator:**  are the subclasses overriding the factory method to return differnet objects.
  **Product:** is the interface, which can be by many other product types. Creator mainly returns the products objects.
  **Concrete Product:** are the objects we want to create, so that we can use them in our code.

  ### Example
  Here, we are using an open source framework and it only provides ```Square``` button. But we need a Round Shape Button. So we extend the ```Button``` class and create our subclass ```RoundButton``` and add our own implementaions. But now we have to tell the factory to create our ```RoundButton```. We can simply extend our base framwork and override its ```createButton``` method which return ```RoundButton``` objects.

  ### When to use Factory Pattern
  - When we want to provide users of our library or framework with a way to extend its internal components.
  - When we don’t know beforehand the exact types and dependencies of the objects our code should work with.
 
  ### When not to use
  - When we only need to hide some conditional statements in a simple application.
  
