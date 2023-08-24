# SOLID Design Principles
SOLID is a short form for the five object-oriented design (OOD) principles by Robert C. Martin. The illustration below represents the full form for SOLID design principles.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/a283948d-d9e5-4ddb-a842-d5e12c3f9a74" width=50% height=30%>

## Why use SOLID principles?
- Helps to create more understandable and maintainable code
- Reduces tight coupling
- Increases extensibility and modularity

## SOLID
### Single Responsibility Design
- A class should have only one purpose.
- All the data members and function will work towards attaining a common goal.
  Example: We have a class ```Product``` which have multiple attributes. Another class ```Order``` have other attributes along with a method ```calculateDiscount()```.
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d0e8a2db-bad4-48ec-8182-d035fd37df8f" width=30% height=40%>

  But the problem occurs when we try to change the mechanism or logic to calculate the discount. This breaks the rule which states, "A class should have only one reason to change." So, without modifying the ```order``` class, we can create another class ```DiscountCalculator``` and move the methods according to it. SO, changes can be only made on that class.
   
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/43045c72-9751-453f-88bc-6899c3c174b1" width=50% height=40%>

### Open Closed Principle
- OCP can be defined as:
  > Open for extension, but closed for modification
- It helps to extend any system without modifying the existing one.
- Always protected from error while introducing new code into the system.
  Example: We have a class ```Calculator``` which has basic functionality. Now we want to extend some features into our calculator system. According to the principle, we are allowed to extend. So we can extend the ```Calculator``` class and new functionality without modifying the ```Calculator``` class.
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/16f3076e-6c07-40da-814b-0e67b3e6c401" width=50% height=20%>

### Liskov Subsititution Principle
- It povides the use of inheritance in the design so that Super class objects can be replaced by the objects of subclass.
- Avoids the generalization concept. It means we can design such system using this principle where same type of real world objects may have different ways to implement it's function.
  Example:
  Let's construct a simple class called Vehicle that has some attributes and methods and a subclass Car that extends it as shown below:
  
   <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/5054cb30-265b-4db0-8a17-8b887f28d3ac" width=20% height=5%>
   
  Now we want to add some more features like, adding another class ```Bicycle```. We want to extend the ```Vehicle``` class like OCP.  A bicycle is a vehicle, but it does not have an engine. Therefore, the Bicycle class should not be allowed to override the ```startEngine()``` method.
  A possible solution to this issue would be to add two subclasses of ```Vehicle``` that classify the vehicles as motorized vehicles and manual vehicles as follows:
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/fe72931a-640b-41f8-b892-d739652f43b4" width=30% height=2%>
  
### Interface Segregation Principle
- It does not recommend having methods that an interface would not use and require. So, Unnecessary methods in an interface can cause all the implementing class to implement those unnecessary method which makes the system hard to maintain.
- That means, it provide more precise code design with proper abstraction.
  Example: In this example, we have ```Square```, ```Rectangle``` and ```Cube``` class are implementing the ```Shape``` interface which have ```area()``` and ```volume()``` method. But, ```Sqaure``` and ```Rectangle``` can't have any ```volume()``` method. So, they are forced to implement the method.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/5a659237-d147-4c13-90a5-0bdb30cd0d54" width=30% height=20%>

The possible soultion is:

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/abeb31b8-19c0-466b-88d8-8a3ec050e3bd" width=30% height=20%>

Now, there are two interfaces present: ```Shape``` and ```Shape3D```. The Shape interface contains only the methods that are required for 2-D shapes like squares, rectangles, etc., while the ```Shape3D``` interface inherits the methods of the Shape interface and itself only contains methods for 3-D shapes like cubes, spheres, etc.

### Dependency Inversion Principle
- The principle states: Low level modules shouldn't be depend on high level modules, but rather both should depend on abstractions.
- As a result, modules are decoupled and can be useful in case of maintenance and testing.
  Example: Let's look at the below diagram. All the low level class are dependent on ```Manager``.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d6bea928-50ec-4eda-ab10-49cb39001782" width=30% height=20%>

If we want to add another type of employee, we must change the ```Manager``` class which is against the OCP principle. We can use an abstraction between ```Manager``` and other employee classes so that we don't need to change the ```Manager``` class everytime when we add a new employee.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/23a096cf-70e5-45bd-8cc2-b61b90e1a5ee" width=30% height=20%>



