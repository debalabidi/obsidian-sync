##### Inheritance:
- Very class in java extends the super class object. 
- Any class the does not explicitly extend will end up extending the object class. 
- It is highly recommended to over write hashCode(), toString() and equals() method.

##### Object Class:
It serves two main purpose:
1. Acts as a polymorphic type for the methods that need to work on any class that you or anyone else makes. 
2. to provide real method code that all objects in Java need at runtime.

##### When to do inheritance:
- [ ] Check for is a vs has a relationship
- [ ] One class is more specific type of the super class.
- [ ] Consider when you have common behavior implemented of the same type. (Not the best way to implement behavior that is flexible)
- [ ] Do not use inheritance for code reuse always check the is a vs has a relationship.
- [ ] Inheritance hirearchies are usually wide and not deep. But there is no limit to it. 

##### Advantages of Inheritance:
- Get rid of duplicate code by abstracting common behavior.
- Define a common protocol for a group of classes.
- It guarantees that all classes under a super type will have functionality possessed by the super class. 

##### Polymorphism
- The object type and reference type can be different. It can be a super class. This is polymorphic variable.
- If you pass in the super type into method arguments, you get to decide at runtime the behavior by passing the sub class. 
- With polymorphism you can write code that doesn't need to change when you introduce a new sub class into the code. 
- Abstract methods exist for polymorphism.
- The compiler decides whether you can call a method based on the _reference_ type, not the actual object type.
- 

##### Things preventing from making a sub class:
1. If the class has private constructors.
2. Access control. A non public class can only be subclasses by classes of the same package. Classes of different package will not be able to subclass or even use the class. 
3. A final class can not be subclasses.
4. A private class which is basically an inner class.

##### Final class
- When we want security for certain behavior. Like how strings behave. 

##### Overloading vs Overriding
- Overloading is nothing but having the same method name but different parameters. Nothing to do with inheritance or polymorphism. 
	1. The return types can be different.
	2. The return types cant be the only difference. The parameters have to be overloaded. 
	3. You can vary the access level in any direction unlike overriding where it has to be more accessible than the super type.

##### Rules of Overriding
- Methods are the contract.
1. Arguments and return types of a method must be same. 
2. Methods cannot be less accessible. (this would cause runtime issues of something being unavailable,  so compiler will stop it)
3. ???

##### Abstract vs Concrete
- No implementation vs implementation present. 
- Abstract differs to subclass.


##### Interfaces
- It solves multiple inheritance problem.
- Make all methods abstract hence sub classes have to override it. 
- It is a 100% pure abstract class.
- It can have static and default methods. 
- They give you the polymorphic abilities.

##### Class vs subclass vs abstract vs interface
-   Make a class that doesn’t extend anything (other than Object) when your new class doesn’t pass the IS-A test for any other type.
-   Make a subclass (in other words, _extend_ a class) only when you need to make a _**more specific**_ version of a class and need to override or add new behaviors.
-   Use an abstract class when you want to define a _**template**_ for a group of subclasses, and you have at least _some_ implementation code that all subclasses could use. Make the class abstract when you want to guarantee that nobody can make objects of that type.
-   Use an interface when you want to define a **_role_** that other classes can play, regardless of where those classes are in the inheritance tree.



### Notes on Polymorphism
-   When you don’t want a class to be instantiated (in other words, you don’t want anyone to make a new object of that class type), mark the class with the abstract**` keyword.
-   An abstract class can have both abstract and non-abstract methods.
-   If a class has even _one_ abstract method, the class must be marked abstract.
-   An abstract method has no body, and the declaration ends with a semicolon (no curly braces).
-   All abstract methods must be implemented in the first concrete subclass in the inheritance tree.
-   Every class in Java is either a direct or indirect subclass of class **Object**(java.lang.Object).
-   Methods can be declared with Object arguments and/or return types.
-   You can call methods on an object _only_ if the methods are in the class (or interface) used as the _reference_ variable type, regardless of the actual _object_type. So, a reference variable of type Object can be used only to call methods defined in class Object, regardless of the type of the object to which the reference refers.
-  


##### Life of Objects 

- Methods and local variables live on the stack including method parameters.
- Instance variables live inside the object on the heap regardless of the reference being at the method level. 
- Methods are stacked. Top one gets executed first. (Also called the call stack)
 
- Instance variables live within the object they belong to, on the Heap.
-   If the instance variable is a reference to an object, both the reference and the object it refers to are on the Heap.
-   A constructor is the code that runs when you say new on a class type.
-   A constructor must have the same name as the class, and must not have a return type.
-   You can use a constructor to initialize the state (i.e., the instance variables) of the object being constructed.
-   If you don’t put a constructor in your class, the compilerwill put in a default constructor.
-   The default constructor is always a no-arg constructor.
-   If you put a constructor.any constructor.in your class, the compiler will not build the default constructor.
-   If you want a no-arg constructor and you’ve already put in a constructor with arguments, you’ll have to build the no-arg constructor yourself.
-   Always provide a no-arg constructor if you can, to make it easy for programmers to make a working object. Supply default values.
-   Overloaded constructors means you have more than one constructor in your class.
-   Overloaded constructors must have different argument lists.
-   You cannot have two constructors with the same argument lists. An argument list includes the order and type of arguments
-   Instance variables are assigned a default value, even when you don’t explicitly assign one. The default values are 0/0.0/false for primitives, and null for references.

A constructor can have a call to this() or super() but not both.

##### Object Killers
1. Reference goes out of scope permanently.
2. Assign the reference to another object.
3. Explicitly set the reference to null.


##### Numbers and Static

- Static methods are like global methods.
- Static methods never use instance variable values.
- Keyword static lets us run the method without an instance of the class.
	- Not dependent on instance variable but on class. 
- Static method is called using class name.
- Free to combine static and non static methods. But if you have a non static method there must be a way to instantiate the class via:
	- New operator
	- Deserialization
	- Reflection.
- Static methods cannot use instance variables it does not know which values to use. 
- Static methods cannot use non static methods either.
- You can call static methods using reference variable but that makes it less readable and confusing. 
- Static variable values is the same for all instances. 
- Static variables are shared.
- All instances of the class share the same static variable. One per class.
- Static variables are initialized when the class is loaded.
- Two guarantees for static variable initialization
	- static variables are initialized before any object is created 
	- Static variables are initialized before any static method runs. 
- Static final variables are constants.
- Static initializer runs before any code of the class runs. It is a great place to initialize static final variables.

##### Final:
- Final variable means you cant change teh value of the variable.
- Final method means you cannot override the method.
- Final class means you cannot extend the class.


### Data structures and collections
- Natural ordering - Alphabetically. Collections.sort() , for simple objects like strings, numbers etc.
- Collections.sort() - will not compile for objects.



##### Generics
- basically means more type safety.
- Without generics the compiler wouldn't care what you put in the collections. Before generics there was no way to limit the type of object going into an arraylist. 
- There are dozens of things about generics need to be familiar.
- You can create generic classes and is advanced.

##### Important points about Generics

1. Creating an instances of generic classes (like arraylist) new ArrayList<Dog>()
2. Declaring and assigning variables of generic types , List<Dog> = new ArrayList<Dog>()
3. Declaring and invoking methods that take generic types.







