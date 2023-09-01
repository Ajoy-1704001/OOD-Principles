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
  
  <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/32a94f8d-ffc0-44f0-8890-fa647657aafb" width=60% height=50%>

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
