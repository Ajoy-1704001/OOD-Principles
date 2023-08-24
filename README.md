# SOLID Design Principles
SOLID is a short form for the five object-oriented design (OOD) principles by Robert C. Martin. The illustration below represents the full form for SOLID design principles.

<img src="https://github.com/Ajoy-1704001/OOP/assets/57573642/67601eed-8b99-431d-a489-0f15b2eee670" width=70% height=60%>

## Why use SOLID principles?
- Helps to create more understandable and maintainable code
- Reduces tight coupling
- Increases extensibility and modularity

## SOLID
### Single Responsibility Design
- A class should have only one purpose.
- All the data members and function will work towards attaining a common goal.
  Example: We have a class ```Product``` which have multiple attributes. Another class ```Order``` have other attributes along with a method ```calculateDiscount()```.
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d0e8a2db-bad4-48ec-8182-d035fd37df8f" width=70% height=60%>

  But the problem occurs when we try to change the mechanism or logic to calculate the discount. This breaks the rule which states, "A class should have only one reason to change." So, without modifying the ```order``` class, we can create another class ```DiscountCalculator``` and move the methods according to it. SO, changes can be only made on that class.
   
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/43045c72-9751-453f-88bc-6899c3c174b1" width=70% height=60%>

### Open Closed Principle
- OCP can be defined as:
  > Open for extension, but closed for modification
- It helps to extend any system without modifying the existing one.
- Always protected from error while introducing new code into the system.

### Liskov Subsititution Principle
- It povides the use of inheritance in the design so that Super class objects can be replaced by the objects of subclass.
- Avoids the generalization concept. It means we can design such system using this principle where same type of real world objects may have different ways to implement it's function.

### Interface Segregation Principle
- It does not recommend having methods that an interface would not use and require. So, Unnecessary methods in an interface can cause all the implementing class to implement those unnecessary method which makes the system hard to maintain.
- That means, it provide more precise code design with proper abstraction.


### Dependency Inversion Principle
- The principle states: Low level modules shouldn't be depend on high level modules, but rather both should depend on abstractions.
- As a result, modules are decoupled and can be useful in case of maintenance and testing.
