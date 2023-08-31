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
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/981b47c1-0ae6-4c11-ac8b-d4ef427744b9" width=55% height=40%>

  **Creator:** can be an abstract class or concrete class which should define the factory method.
  **Concrete Creator:**  are the subclasses overriding the factory method to return differnet objects.
  **Product:** is the interface, which can be by many other product types. Creator mainly returns the products objects.
  **Concrete Product:** are the objects we want to create, so that we can use them in our code.

  ### Example
  Here, we are using an open source framework and it only provides ```Square``` button. But we need a Round Shape Button. So we extend the ```Button``` class and create our subclass ```RoundButton``` and add our own implementaions. But now we have to tell the factory to create our ```RoundButton``` instead of default button. We can simply extend our base framwork and override its ```createButton``` method which return ```RoundButton``` objects.

  ### When to use Factory Pattern
  - When we want to provide users of our library or framework with a way to extend its internal components.
  - When we don’t know beforehand the exact types and dependencies of the objects our code should work with.
 
  ### When not to use
  - When we only need to hide some conditional statements in a simple application.

## Strategy Pattern
- It's intent is to provide a mechanism to select/run different algorithm or strategy.
- It encapsulates the part of the system which varies frequently.
- It gives a class the ability to perform a certain task in different ways or strategies, without that class knowing the implementation details of any strategy.
- It doesn't care about how the strategy is created, it only deals with running strategy from the context class.

### Main Components

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/caf7fc72-83d0-4452-bfa0-26f5a6f214da" width=40% height=40%>

**Context:** It maintains a reference to the concrete strategy.
**Strategy:** is a common interface for implementing all concrete strategies.
**Client:** creates a strategy object and tells context to use that strategy. Client can replace the strategy depending on the need at runtime.

### Example:
Here we have different options to pay. Each payment option has it's own algorithm or set of procedures. Using Strategy Design Pattern, user can choose a payment option at runtime and process the payment. ```Client``` will inform the ```PaymentContext``` about the ```PaymentStrategy```. ```PaymentContext``` will process the payment using the delegated methods of ```PaymentStrategy``` concrete object.

### When to use Strategy Pattern
- When we have to change algorithm/strategy dynamically at run time.
- When the class has a massive conditional statement that switches between different variants of the same algorithm.

### When not to use
- When we have a small number of algorithms to change, or one algorithm which will never change.

## Decorator Pattern
- It adds new functionality to objects without modifying their defining classes.
- Can be thought of as a wrapper or more formally a way to enhance or extend the behavior of an object dynamically. It favors composition over inheritance.
- Decorator classes mirror the type of the components they decorate.
- It usually insert decorators transparently and the client never has to know it’s dealing with a decorator.
- It truely follows the **OCP** principle and divide the classes to follow **SRP**.

  ### Main Components

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d16b4246-c5f0-402f-a047-0a680f3da2d3" width=50% height=40%>

  **Component:** is an common interface for both the components(wrapped objects) and decorators(wrapper).
  **Concrete Component:** are the classes of objects that are going to be wrapped.
  **Base Decorator:** It mainly holds the reference of the wrapped objects. So it achieves all the method of the wrapped objects.
  **Concrete Decorator:** Now, if we want to add some extra functionality to add to the components dynamically, we can override methods or add our own methods.

  ### Example
  Suppose, we have a ```Pizza``` interface. We create a ```PlainPizza``` class implementing the ```Pizza``` interface. But, I want to add some cheese in the pizza. Again, one of my friend wants some extra sauce in the pizza. After that, I also want another pizza with both extra cheese and sauce in the pizza. So, creating those different pizza's from ```Pizza``` interface using inheritance, cost lots of redundant code. So, here comes the decorator pattern. Decorator are the same type as the component, so basically it wraps the ```PlainPizza``` and decorates it with its own behavior. Using different types of concrete decorator, we can wrap each other and get our desired pizza.
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/5ae45ae9-78b0-45b6-a4e8-86bde740be62" width=50% height=30%>

  ### When to use Decorator Pattern
  - When we want to be able to assign extra behaviors to objects at runtime without breaking the code that uses these objects.
  - When inheritance can cause problem extending an object's behavior or inheritance is not possible.
  
# M
### Why factory method relies on inheritance?
