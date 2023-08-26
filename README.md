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
### 1. Single Responsibility Principle
- A class should have only one purpose.
- All the data members and function will work towards attaining a common goal.
  
  Example: We have  class two ```Product``` and ```Order``` which have multiple attributes. ```Order``` class have a method ```calculateDiscount()```.
  Visual representation of above scenario is given below:
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/32a94f8d-ffc0-44f0-8890-fa647657aafb" width=30% height=40%>

  **Violation**
  Class ```Order``` is all about order details. But, it has a method ```calculateDiscount()``` method which causes the violation of SRP. Suppose, we want to change the inside logic to calculate discount in future. For this reason, we need to change the ```Order``` class which breaks the rule which states, "A class should have only one reason to change". That means ```Order``` have only one job to do which is handling order.
  **Possible Solution**
Without modifying the ```Order``` class, we can create another class ```DiscountCalculator``` and move the methods according to it. So, changes can be only made on ```DiscountCalculator``` class in future. And it preserves the SRP rule.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d6780cf5-9ea0-4806-9123-2a9d9840acd2" width=50% height=40%>

### 2. Open Closed Principle
- OCP can be defined as:
  > Open for extension, but closed for modification
- It helps to extend any system without modifying the existing one.
- Always protected from error while introducing new code into the system.
  Example: We have a class ```Calculator``` which has basic functionality. Now we want to extend some features into our calculator system. According to the principle, we are allowed to extend. So we can extend the ```Calculator``` class and new functionality without modifying the ```Calculator``` class.
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/42fb5d4a-bad4-4396-a968-e272deae2571" width=50% height=20%>

### 3. Liskov Subsititution Principle
- It provides the use of inheritance in the design so that Super class objects can be replaced by the objects of subclass.
- Avoids the generalization concept. It means we can design such system using this principle where same type of real world objects may have different ways to implement it's function.
  Example:
  Let's construct a simple class called Vehicle that has some attributes and methods and a subclass Car that extends it as shown below:
  
   <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/5a3c409e-9ff1-4006-ae26-383452b7ec39" width=10% height=2%>
   
  Now we want to add some more features like, adding another class ```Bicycle```. We want to extend the ```Vehicle``` class like OCP.  A bicycle is a vehicle, but it does not have an engine. Therefore, the Bicycle class should not be allowed to override the ```startEngine()``` method.
  A possible solution to this issue would be to add two subclasses of ```Vehicle``` that classify the vehicles as motorized vehicles and manual vehicles as follows:

  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/89d1fe0a-e47d-45df-aa43-b34009441d69" width=20% height=10%>
  
### 4. Interface Segregation Principle
- It does not recommend having methods that an interface would not use and require. So, Unnecessary methods in an interface can cause all the implementing class to implement those unnecessary method which makes the system hard to maintain.
- That means, it provide more precise code design with proper abstraction.
  Example: In this example, we have ```Square```, ```Rectangle``` and ```Cube``` class are implementing the ```Shape``` interface which have ```area()``` and ```volume()``` method. But, ```Square``` and ```Rectangle``` can't have any ```volume()``` method. So, they are forced to implement the method.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/cf1b63cf-3d3c-4c75-bf0b-ed52462eac23" width=30% height=25%>

The possible soultion is:

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/b969d210-b975-4c47-977e-3cf2db59c0a1" width=30% height=25%>

Now, there are two interfaces present: ```Shape``` and ```Shape3D```. The Shape interface contains only the methods that are required for 2-D shapes like squares, rectangles, etc., while the ```Shape3D``` interface inherits the methods of the Shape interface and itself only contains methods for 3-D shapes like cubes, spheres, etc.

### 5. Dependency Inversion Principle
- The principle states: Low level modules shouldn't be depend on high level modules, but rather both should depend on abstractions.
- As a result, modules are decoupled and can be useful in case of maintenance and testing.
  Example: Let's look at the below diagram. All the low level class are dependent on ```Manager```.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/ebfbbefd-2e2e-48e2-9750-6e36d8364530" width=30% height=20%>

If we want to add another type of employee, we must change the ```Manager``` class which is against the OCP principle. So, the solution is: We can use an abstraction between ```Manager``` and other employee classes so that we don't need to change the ```Manager``` class everytime when we add a new employee.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/3bc1f506-0476-40a4-bcd4-e50696f638f0" width=30% height=25%>

