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
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/32a94f8d-ffc0-44f0-8890-fa647657aafb" width=40% height=40%>

  **Violation**
  
  Class ```Order``` is all about order details. But, it has a method ```calculateDiscount()``` method which causes the violation of SRP. Suppose, we want to change the inside logic to calculate discount in future. For this reason, we need to change the ```Order``` class which breaks the rule which states, "A class should have only one reason to change". That means ```Order``` have only one job to do which is handling order.
  **Possible Solution**
  
Without modifying the ```Order``` class, we can create another class ```DiscountCalculator``` and move the methods according to it. So, changes can be only made on ```DiscountCalculator``` class in future. And it preserves the SRP rule.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/d6780cf5-9ea0-4806-9123-2a9d9840acd2" width=50% height=50%>

### 2. Open Closed Principle
- OCP can be defined as:
  > Open for extension, but closed for modification
- It helps to extend any system without modifying the existing one.
- Always protected from error while introducing new code into the system.
  Example: We have two option for payment ```Bkash``` and ```Rocket``` which have a method ```initialize``` to initialize the payment gateway. There is another class ```Payment``` which starts processing the payment options depending on the user choice of payment.

  **Violation**

  For customer satisfaction, the authority decided to integrate another payment option ```Nagad```. In this case, we have to modify the ```Payment``` class to process the ```Nagad``` class instance. This violates the OCP.
  
 <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/bfe5b13b-9328-4656-b19c-1ff948ce0a1c" width=70% height=40%>

**Possible Solution**

We can introduce an abstraction level between payment processing and payment options. If new payment option is integrated into the system, it can implement the interface ```PaymentOption``` and we don't need to modify the ```Payment``` class.

 <img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/26358ef5-52f9-4217-95cb-4e66670cb289" width=50% height=40%>


### 3. Liskov Subsititution Principle
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
  
### 4. Interface Segregation Principle
- It does not recommend having methods that an interface would not use and require. So, Unnecessary methods in an interface can cause all the implementing class to implement those unnecessary method which makes the system hard to maintain.
- That means, it provide more precise code design with proper abstraction.
  Example: In this example, we have ```Square```, ```Rectangle``` and ```Cube``` class are implementing the ```Shape``` interface which have ```area()``` and ```volume()``` method.

  **Violance**

  But, ```Square``` and ```Rectangle``` can't have any ```volume()``` method. So, they are forced to implement the method. It breaks the ISP rule.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/cf1b63cf-3d3c-4c75-bf0b-ed52462eac23" width=30% height=25%>

**Possible Solution**

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/b969d210-b975-4c47-977e-3cf2db59c0a1" width=30% height=25%>

Now, there are two interfaces present: ```Shape``` and ```Shape3D```. The Shape interface contains only the methods that are required for 2-D shapes like squares, rectangles, etc., while the ```Shape3D``` interface inherits the methods of the Shape interface and itself only contains methods for 3-D shapes like cubes, spheres, etc.

### 5. Dependency Inversion Principle
- The principle states: Low level modules shouldn't be depend on high level modules, but rather both should depend on abstractions.
- As a result, modules are decoupled and can be useful in case of maintenance and testing.
  Example: Let's look at the below diagram. All the low level class are dependent on ```Manager```.
  
<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/ebfbbefd-2e2e-48e2-9750-6e36d8364530" width=30% height=20%>

**Violance**

If we want to add another type of employee, we must change the ```Manager``` class which is against the OCP principle. 

**Possible Solution**

So, the solution is: We can use an abstraction between ```Manager``` and other employee classes so that we don't need to change the ```Manager``` class everytime when we add a new employee.

<img src="https://github.com/Ajoy-1704001/OOD-Principles/assets/57573642/3bc1f506-0476-40a4-bcd4-e50696f638f0" width=30% height=25%>

