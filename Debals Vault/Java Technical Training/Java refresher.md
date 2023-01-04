When designing the object class think about the objects that will be created from the class type. Think about:
	 - things the object knows. (instance variables / state)
	 - things the object can do. (methods / behavior)

A class is not an object but a blueprint to create an object. The JVM takes the class and out of that it knows how to create an object. 

Each time an object is created it goes into an area of memory called The heap. The heap is called garbage collectable heap.

What if I need global variables and methods? How do I do that if everything has to go in a class?
	- There is no concept of global but you can have static methods and static classes. 

Variables are of two types
	- Primitives (actual values)
	- references (a way to get to the object in the heap)

