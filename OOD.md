# SOLID Design Principles
SOLID is a short form for the five object-oriented design (OOD) principles by Robert C. Martin. The illustration below represents the full form for SOLID design principles.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/a97754c8-c49e-4e00-9c56-18f9a584fe2e" width=50% height=30%>

> Image Reference : https://www.educative.io/

## Why use SOLID principles?
- Helps to create more understandable and maintainable code
- Reduces tight coupling
- Increases extensibility and modularity
- Testing becomes easy

## SOLID
### Single Responsibility Principle
- A class should have only one purpose.
- All the data members and function will work towards attaining a common goal.
- It should have only one reason to change.
  
  Example: We have  class two ```Product``` and ```Order``` which have multiple attributes. ```Order``` class have a method ```calculateDiscount()```.
  Visual representation of above scenario is given below:
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/32a94f8d-ffc0-44f0-8890-fa647657aafb" width=50% height=40%>

  **Violation**
  
  Class ```Order``` is all about order details. But, it has a method ```calculateDiscount()``` method which causes the violation of SRP. Suppose, we want to change the inside logic to calculate discount in future. For this reason, we need to change the ```Order``` class which breaks the rule which states, "A class should have only one reason to change". That means ```Order``` have only one job to do which is handling order.
  
  **Possible Solution**
  
  Without modifying the ```Order``` class, we can create another class ```DiscountCalculator``` and move the methods according to it. So, changes can be only made on ```DiscountCalculator``` class in future. And it preserves the SRP rule.

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d6780cf5-9ea0-4806-9123-2a9d9840acd2" width=60% height=50%>

### Liskov Subsititution Principle
- It provides the use of inheritance in the design so that Super class objects can be completely replaced by the objects of subclass.
- Avoids the generalization concept. That requires the objects of your subclasses to behave in the same way as the objects of your superclass.
  Example:
  Suppose we have a class ```Mobile``` which has some attributes and methods and few subclass ```Iphone```and ```Pixel```.

  **Violation**

  Let's add a new feature/feature ```Nokia``` which is also a mobile. But, it doesn't have any method ```findMyPhone()``` method. So, there is no need to override the ```findMyPhone``` method. As a result, base can't be fully replaced by the subclass.

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/f40b79d6-604d-4277-9d38-aedbeee84f91" width=40% height=40%>

  **Possible Solution**
   
  A possible solution to this issue would be to add two subclasses of ```Mobile``` that classify the mobiles as ```SmartPhone``` and ```Nokia``` as follows:

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/65779144-96ab-47fe-a98d-99564db43ec9" width=50% height=30%>

# Design Pattern

Design pattern is a general repeatable solution to a commonly occurring problem in software design.

## Why do we need design pattern?
1. Provides proven development paradigm.
2. Saves time without having to reinvent pattern everytime a problem arise.
3. Promotes reusability.
4. Enables developer/designers to share a common vocabulary in system design.

# Classification of Design Patterns
There are different types of design pattern. These are differed from each other on the basis of complexity, details level, intent and scale of applicability to the entire system being design. Design Patterns are mainly classified into three categories. Such as:

1. Creational Design Pattern: It provides mechanism to create objects without revealing the creation method that enhance the flexibilities and reusability of the existing code. Example: Factory, Builder, etc.
2. Structural Design Pattern: It is about class-object composition i.e. classes combined together to form a bigger structure for achieving multiple goals altogether. Example: Decorator, Facade, etc.
3. Behavioral Design Pattern: This pattern type is concerned with the communication between objects and the assignment of responsibilities between objects, or, encapsulating behavior in an object and delegating requests to it. Example: Observer, Strategy, etc.

## Factory Pattern
- It encapsulates object creation logic.
- Defines an interface for creating an object, but let subclass decide which class to instantiate.
- Factory method depends on inheritance. [How?](#miscellaneous)
- All factory patterns promote loose coupling. [How?](#miscellaneous)
- The Factory Pattern helps us to align with the Dependency Inversion principle.
  ### Main Components
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/981b47c1-0ae6-4c11-ac8b-d4ef427744b9" width=55% height=40%>

  **Creator:** can be an abstract class or concrete class which should define the factory method.
  
  **Concrete Creator:**  are the subclasses overriding the factory method to return differnet objects.
  
  **Product:** is the interface, which can be by many other product types. Creator mainly returns the products objects.
  
  **Concrete Product:** are the objects we want to create, so that we can use them in our code.

  ### Example
  Here, we are using an open source framework and it only provides ```Square``` button. But we need a Round Shape Button. So we extend the ```Button``` class and create our subclass ```RoundButton``` and add our own implementaions. But now we have to tell the factory to create our ```RoundButton``` instead of default button. We can simply extend our base framwork and override its ```createButton``` method which return ```RoundButton``` objects.
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/2c3c0dcf-7a5e-491d-b8f5-303be6effa5b" width=55% height=40%>

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

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/caf7fc72-83d0-4452-bfa0-26f5a6f214da" width=50% height=50%>

**Context:** It maintains a reference to the concrete strategy.

**Strategy:** is a common interface for implementing all concrete strategies.

**Client:** creates a strategy object and tells context to use that strategy. Client can replace the strategy depending on the need at runtime.

### Example:
Here we have different options to pay. Each payment option has it's own algorithm or set of procedures. Using Strategy Design Pattern, user can choose a payment option at runtime and process the payment. ```Client``` will inform the ```PaymentContext``` about the ```PaymentStrategy```. ```PaymentContext``` will process the payment using the delegated methods of ```PaymentStrategy``` concrete object.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/1c0b4e79-48bf-4f16-b5ef-1a1d8f9d4960" width=60% height=60%>

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

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d3e121b2-49fb-48a2-92a3-606f2defc9ef" width=50% height=30%>

  ### When to use Decorator Pattern
  - When we want to be able to assign extra behaviors to objects at runtime without breaking the code that uses these objects.
  - When inheritance can cause problem extending an object's behavior or inheritance is not possible.
  
# Miscellaneous [back to top](#factory-pattern)
### Why factory method relies on inheritance?

The factory method pattern relies on inheritance, as object creation is inherited to subclasses that implement the factory method to create objects. Concrete class of ```Creator``` interface overrides the object creation method and creates object according to the concrete class. So, subclasses mainly use polymorphism of ```createObject``` via inheritance.

### How factory pattern promotes loose coupling?

The client always communicates with the factory interface/abstract class so that it will only work with the subclasses. On the other hand, subclasses decide which object to create. So, it reduces the dependency between client and concrete classes. This is how factory pattern achieves loose coupling.

