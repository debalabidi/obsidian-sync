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

1. Creating an instances of generic classes (like arraylist) 
	1. `new ArrayList<Dog>()`
2. Declaring and assigning variables of generic types , 
	1. `List<Dog> = new ArrayList<Dog>()`
3. Declaring and invoking methods that take generic types.


##### Using Generic Class

- Arraylist is the most used generic class.
- Two key areas to look at are:
	- The class declaration.
	- The method declaration that lets you add elements.

` public class ArrayList<E> extends AbstractList<E> implements List<E>`

`Public Boolean add(E o)`

The E represents the object that would be passed into the method. It is called the type parameter.


##### Using generic methods

- Generic class means that the class declaration uses type parameter.
- Generic method means that the method uses type parameter.
- Type parameters can be used in different ways
	- Using type parameter defined in the class declaration. 
	- Using type parameter not defined in the class declaration
		- If the class does not use type parameter, then you can still specify the Type parameter before the return type. That says that T can be of any type animal.

`public <T extends Animal> void takeThing(ArrayList <T> list)`

`public void takeThing(ArrayList<Animal> list)`

The first one can take any type of sub class of animal while the second one can not take a subtype of animal and only take in an Animal. It does gives the illusion of breaking polymorphism.

In generics extends means extend or implements.

Comparable provides you with the ability to compare two objects, one itself and the other that is passed in. 

A comparator class allows you to pass in a class with a custom sort, so you can have a class that sorts by artist or title. 

You can use an inner class to avoid the boiler plate code but it is still verbose.

You can use lambdas. 

SAM (Single Abstract Method) / Functional Interfaces they only have one abstract method.

Collection API's have three main interfaces:
1. List
2. Set
3. Maps


List is used when sequence matters. Collection know about index position. List know where something is in the list. You can have more than one element referencing the same object.

Set is used when uniqueness matters. Collection that do not allow duplicates. You can never have more than one element referencing the same object. 

Maps is used when finding something by key matters. Collection uses key value pairs. Maps know the value associated with the given key. You can have two keys referencing the same value but you cannot have two duplicate keys. 


##### What makes two objects equal

Reference equality vs Object Equality

Reference Equality: Two references one object on the heap. If you call the hashCode method on them you will get the same result. If you do not override the hashCode method you inherit it from the class object. Usually the objects memory address is used to generate the hashCode so that no two objects have the same address.


Object Equality: Two references and two objects on the heap but from business standpoint they are equal. If we want to treat both objects to be equal then you have to override both hashcode() and equals() method. You override the equals to ensure that the attributes or the uniqueness is the same and then hashcode is overridden to ensure that they are the same. 

##### How Hashset checks for duplicates : hashcode() and equals()

When you put an object into hashset it calls the objects hashcode method to determine where to put the object in the hashset. It compares the hashcode of other objects as well and if there is not a duplicate then it assumes it is unique. So you need to override the hashcode so to ensure that the hashcode is the same for when two objects are fundamentally equal. 

So if the hashset encounters an object trying to be inserted the that has the same hashcode() then it calls the equals method and see if they are really equal. If equal the object is not added to the hashset. 


##### Class object states rules you may follow

- If two objects are equal they must have the same hashcode
- If two objects are equal then calling the equals method on either object will return true
- If two objects has the same hashcode value they are not required to be equal but if they are equal they need to have the same hashcode
- If you override equals you must over hashcode
- Default behavior of hashcode is to generate a number, so if you do not override then two objects can never be equal. 
- Default behavior of equals is to do a == test. Therefore if you do not override then no two objects can ever be equal since the references will have different values. 
- 



TreeSet is always sorted. And prevents duplicates. In order to use TreeSet the objects that go inside a TreeSet must implement a comparable interface or the TreeSet instance needs to take in a comparator. 

##### Maps

Each element in a map has two objects



If we want to return a list that is not modifiable then we can pass our collection through the Collections.unmodifiableList () method.

As of Version 9, java has convience factory methods for collections, they allow you to create a prefilled list, set, or map. There are couple of things to understand about them. 


The resulting collection created by these convience methods cannot be modified, they cannot even be sorted. They are not standard collections.

Convience methods like list.of() , set.of(), map.of()/ Map.ofEntries()

If we take a method that takes a list of object that is type parameterized as a generic. Then we cannot send in a list of type parameterized of subclass generics. This will not work because what happens if inside the method we try to add a different subtype while the list can only take the other one. So the compiler will stop this from happening. In order to get around it you can use the wildcard. This allows you to pass in the list but stops you from adding anything to the list. 

Example of wildcard
`public void takeAnimals (List<? extends Animal> animals)`



`<T extends Animal> void takeThing(List<T> list)`



`public <T extends Animal> void takeAnimals(List<T> list) { }`



The above doesn't do much but the below one allows you return a list with the same type as was passed into the method. 


`public <T extends Animal> List<T> takeAnimals(List<T> list) { }`


With the wildcard below there is no guarantee that the return type will be the same as the type passed into the method.

`public List<? extends Animal> takeAnimals(List<? extends Animal> animals) { }`

Rule: use wildcard when you want to use a sub type or dont care about the return type and use the Type parameter when you want to enforce the type safety.

### Chapter #12 : Lambdas and streams


The Streams API is a set of operations we can perform on a collection, so when we read these operations in our code, we can understand what we’re trying to do with the collection data.

**You don’t need to worry too much about the generic types on the Stream methods; you’ll see that using Streams “just works” the way you’d expect.**

In case you are interested:

-   **`<T>`** is usually the Type of the object in the stream.
    
-   **`<R>`** is usually the type of the Result of the method.

Stream methods that return another Stream are called Intermediate Operations. These are instructions of things to do, but they don’t actually perform the operation on their own.

Streams are like recipes: nothing’s going to happen until someone actually cooks them


Collections are not ingredients, and a list limited to four entries is not a chocolate cake (sadly). But you do need to call one of the Stream’s “do it” methods in order to get the result you want. These “do it” methods are called **Terminal Operations**, and these are the methods that will actually return something to you.


# Stream operations are building blocks

We wrote a lot of code just to output the first four elements in the list. We also introduced a lot of new terminology: streams, intermediate operations, and terminal operations. Let’s put all this together: you create a **stream p****i****peline** from three different types of building blocks.

Get the Stream from a **source** collection.
Call zero or more **intermediate operations** on the Stream.
Output the results with a **terminal operation**.

You need at least the **_first_** and **_last_** pieces of the puzzle to use the Streams API. However, you don’t need to assign each step to its own variable (which we were doing on the last page). In fact, the operations are designed to be **chained**, so you can call one stage straight after the previous one, without putting each stage in its own variable.


# Building blocks can be stacked and combined


**The source, the intermediate operation(s), and the terminal operation all combine to form a Stream Pipeline. This pipeline represents a query on the original collection.**


Create complex pipeline 









