# OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?

The fail fast principle stands for stopping the current operation as soon as any unexpected error occurs. Adhering to this principle generally results in a more stable solution. It might appear counter-intuitive at first. How is it so that failing at any error leads to stability? Isn’t it backward?

Indeed, when you start applying this practice, application crashes might seem overwhelming, especially if you have a working software whose developers didn’t stick to fail-fast before. But if you don’t give up, grit your teeth and fix all the code causing those failures, you will benefit from it greatly.

The trick here is that adhering to the fail fast principle, we improve the feedback loop. We quickly reveal all problems in our software making it easier to spot and fix them.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?

Traverse the whole linked list and count the no. of nodes. Now traverse the list again till count/2 and return the node at count/2.

#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?

A solution is to have a data structure to count the number of iterations of each integer. This solution could be implemented either with an array or a hash table.
An implementation in Java:

public int repeatedNumber(final List<Integer> list) {
  if(list.size() <= 1) {
    return -1;
  }
  
  int[] count = new int[list.size() - 1];

  for (int i = 0; i < list.size(); i++) {
    int n = list.get(i) - 1;
    count[n]++;

    if (count[n] > 1) {
      return list.get(i);
    }
  }

  return -1;
}

#### What is a linked list? How to find if a linked list has a loop?

A linked list is a linear data structure where each element is a separate object. Linked list elements are not stored at contiguous location; the elements are linked using pointers. Each node of a list is made up of two items - the data and a reference to the next node. The last node has a reference to null.

Traverse the list one by one and keep putting the node addresses in a Hash Table. At any point, if NULL is reached then return false and if next of current node points to any of the previously stored nodes in Hash then return true.

#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?


Sorting Algorithms:
Bubble Sort		O(n)	
Heapsort		O(n log n)	
Insertion Sort		O(n)	
Mergesort		O(n log n)	
Quicksort		O(n log n)	
Selection Sort		O(n2)	
Shell Sort		O(n)	
Smooth Sort		O(n)	

Data Structures Comparison: Search/insert/detele
Array	O(n)	N/A	N/A	
Sorted Array	O(log n)	O(n)	O(n)	
Linked List	O(n)	O(1)	O(1)	
Doubly Linked List	O(n)	O(1)	O(1)	
Stack	O(n)	O(1)	O(1)	
Hash table	O(1)	O(1)	O(1)	
Binary Search Tree	O(log n)	O(log n)	O(log n)	
B-Tree	O(log n)	O(log n)	O(log n)	
Red-Black tree	O(log n)	O(log n)	O(log n)	
AVL Tree	O(log n)	O(log n)	O(log n)	

#### How does HashMap work?

HashMap works on the principle of hashing, we have put(key, value) and get(key) method for storing and retrieving Objects from HashMap. When we pass Key and Value object  to put() method on Java HashMap, HashMap implementation calls hashCode method on Key object and applies returned hashcode into its own hashing function to find a bucket location for storing Entry object, important point to mention is that HashMap in Java stores both key and value object as Map.Entry in a bucket which is essential to understand the retrieving logic. 

#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)

String, Integer and other wrapper classes are natural candidates of HashMap key, and String is most frequently used key as well because String is immutable and final,and overrides equals and hashcode() method. Other wrapper class also shares similar property. Immutabiility is required, in order to prevent changes on fields used to calculate hashCode() because if key object return different hashCode during insertion and retrieval than it won't be possible to get object from HashMap. Immutability is best as it offers other advantages as well like thread-safety, If you can keep your hashCode same by only making certain fields final, then you go for that as well. Since equals() and hashCode() method is used during retrieval of value object from HashMap, its important that key object correctly override these methods and follow contact. If unequal object return different hashcode than chances of collision will be less which subsequently improve performance of HashMap.

### Other

#### What is a garbage collector, in a nutshell?

 The garbage collector, or just collector, attempts to reclaim garbage, or memory occupied by objects that are no longer in use by the program.  
 
 The basic principles of garbage collection are to find data objects in a program that cannot be accessed in the future, and to reclaim the resources used by those objects.

Many programming languages require garbage collection, either as part of the language specification (for example, Java, C#, D,[3] Go and most scripting languages) or effectively for practical implementation (for example, formal languages like lambda calculus); these are said to be garbage collected languages. Other languages were designed for use with manual memory management, but have garbage-collected implementations available (for example, C and C++). Some languages, like Ada, Modula-3, and C++/CLI, allow both garbage collection and manual memory management to co-exist in the same application by using separate heaps for collected and manually managed objects; others, like D, are garbage-collected but allow the user to manually delete objects and also entirely disable garbage collection when speed is required.

While integrating garbage collection into the language's compiler and runtime system enables a much wider choice of methods,[citation needed] post-hoc GC systems exist, such as Automatic Reference Counting (ARC), including some that do not require recompilation. (Post-hoc GC is sometimes distinguished as litter collection.) The garbage collector will almost always be closely integrated with the memory allocator.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?

Well, all casting really means is taking an Object of one particular type and “turning it into” another Object type. This process is called casting a variable.

This topic is not specific to Java, as many other programming languages support casting of their variable types. But, as with other languages, in Java you cannot cast any variable to any random type.

Upcasting (Generalization or Widening) is casting to a parent type in simple words casting individual type to one common type is called upcasting while downcasting (specialization or narrowing) is casting to a child type or casting common type to individual type

#### Which order should we catch the exceptions? Why?

When catching multiple exceptions, the Java compiler requires us to place the more specific ones before the more general ones, otherwise they would be unreachable and would result in a compiler error.

### Object-oriented

#### What is a class?

In object-oriented programming, a class is a blueprint for creating objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods). The user-defined objects are created using the class keyword.

#### What is an object?

In computer science, an object can be a variable, a data structure, a function, or a method, and as such, is a value in memory referenced by an identifier.

In the class-based and object-oriented programming paradigms, object refers to a particular instance of a class, where the object can be a combination of variables, functions, and data structures.

#### What is a constructor?

In class-based object-oriented programming, a constructor (abbreviation: ctor) is a special type of subroutine called to create an object. It prepares the new object for use, often accepting arguments that the constructor uses to set required member variables.

A constructor resembles an instance method, but it differs from a method in that it has no explicit return type, it is not implicitly inherited and it usually has different rules for scope modifiers. Constructors often have the same name as the declaring class. They have the task of initializing the object's data members and of establishing the invariant of the class, failing if the invariant is invalid. A properly written constructor leaves the resulting object in a valid state. Immutable objects must be initialized in a constructor.

#### Do we require parameter for constructors?

 A default constructor does not require any parameters for object creation that's why sometimes we declare an object without any parameters.

#### What is an interface?

An interface is a reference type in Java. It is similar to class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface.

Along with abstract methods, an interface may also contain constants, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods.

Writing an interface is similar to writing a class. But a class describes the attributes and behaviors of an object. And an interface contains behaviors that a class implements.

Unless the class that implements the interface is abstract, all the methods of the interface need to be defined in the class.

#### What are access modifiers?

Access modifiers (or access specifiers) are keywords in object-oriented languages that set the accessibility of classes, methods, and other members. Access modifiers are a specific part of programming language syntax used to facilitate the encapsulation of components.

#### What is data hiding?

Data hiding is a software development technique specifically used in object-oriented programming (OOP) to hide internal object details (data members). Data hiding ensures exclusive data access to class members and protects object integrity by preventing unintended or intended changes

#### Can a static method use non-static members?

A static method can access non-static methods and fields of any instance it knows of. However, it cannot access anything non-static if it doesn't know which instance to operate on.

I think you're mistaking by examples like this that don't work:

class Test {
  int x;

  public static doSthStatically() {
    x = 0; //doesn't work!
  }
}
Here the static method doesn't know which instance of Test it should access. In contrast, if it were a non-static method it would know that x refers to this.x (the this is implicit here) but this doesn't exist in a static context.

If, however, you provide access to an instance even a static method can access x.

Example:

class Test {
  int x;
  static Test globalInstance = new Test();

  public static doSthStatically( Test paramInstance ) {
    paramInstance.x = 0; //a specific instance to Test is passed as a parameter
    globalInstance.x = 0; //globalInstance is a static reference to a specific instance of Test

    Test localInstance = new Test();
    localInstance.x = 0; //a specific local instance is used
  }
}

#### What is the difference between hiding a static method and overriding an instance method?

The ability of a subclass to override a method allows a class to inherit from a superclass whose behavior is close enough and then to modify behavior as needed. The overriding method has the same name, number and type of parameters, and return type as the method it overrides. Basically it’s the definition of method hiding in Java.

An overriding method can also return a subtype of the type returned by the overridden method. This is called a covariant return type.

When overriding a method, you might want to use the @Override annotation that instructs the compiler that you intend to override a method in the superclass. If, for some reason, the compiler detects that the method does not exist in one of the superclasses, it will generate an error.

If a subclass defines a class method with the same signature as a class method in the superclass, the method in the subclass hides the one in the superclass.

The distinction between hiding and overriding has important implications. The version of the overridden method that gets invoked is the one in the subclass. The version of the hidden method that gets invoked depends on whether it is invoked from the superclass or the subclass.

#### Define the following terms: Instantiation, Attribute, Method

The process of creating an object from a class is called instantiation because an object is an instance of a class.

In Object-oriented programming(OOP), classes and objects have attributes. Attributes are data stored inside a class or instance and represent the state or quality of the class or instance. In short, attributes store information about the instance.

A method in object-oriented programming (OOP) is a procedure associated with a message and an object. An object consists of data and behavior; these comprise an interface, which specifies how the object may be utilized by any of its various consumers.

#### Could we access a static variable (or method) from a non-static method? Why?

Instance methods can access instance variables and instance methods directly.
Instance methods can access class variables and class methods directly.
Class methods can access class variables and class methods directly.
Class methods cannot access instance variables or instance methods directly—they must use an object reference. Also, class methods cannot use the this keyword as there is no instance for this to refer to.
So the answer is yes, non-static methods CAN access static variables.

#### Could we access a non-static variable (or method) from a static method? Why?

If we need to call the non-static method product from the static method main, then we would have to create an instance of class and call the method from the newly created instance.

#### How many instances you have of a static variable of a given class?

Static variables belong to the class itself, not to objects of the class. There is only one instance of each static variable, and it is shared among all the objects of that class. Different objects cannot have different values for a static variable.

#### Why is it not a good practice to write a lot of static methods?

Creating static methods that take an instance is bad practice because any method that takes an instance should probably be an instance method. On the other hand, things like utility and factory functions generally don't take an instance, so they should be static.

If you're wondering why they're not "pure OO", it's because they are not instance methods. A "pure" OO language would have everything being an object and all functions be instance methods.

#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?

Static methods are the methods in Java that can be called without creating an object of class. They are referenced by the class name itself or reference to the Object of that class.

Static method(s) are associated to the class in which they reside i.e. they can be called even without creating an instance of the class i.e ClassName.methodName(args).
They are designed with aim to be shared among all Objects created from the same class.
Static methods can not be overridden. But can be overloaded since they are resolved using static binding by compiler at compile time.

When to use static methods ??

When you have code that can be shared across all instances of the same class, put that portion of code into static method.
They are basically used to access static field(s) of the class.

#### What is the ‘this’ reference?

The this is a keyword in Java which is used as a reference to the object of the current class, with in an instance method or a constructor. Using this you can refer the members of a class such as constructors, variables and methods

#### What are base class, subclass and superclass?

The class from which the subclass is derived is called a superclass (also a base class or a parent class). Excepting Object , which has no superclass, every class has one and only one direct superclass (single inheritance). A subclass inherits all the members (fields, methods, and nested classes) from its superclass.

#### Draw an object oriented family (as entities, with relations) on the whiteboard.

#### Difference between overloading and overriding?

Overloading occurs when two or more methods in one class have the same method name but different parameters. Overriding means having two methods with the same method name and parameters (i.e., method signature). One of the methods is in the parent class and the other is in the child class.

#### What are the Object Oriented Principles? Explain the concepts with realistic examples!

Encapsulation
The different objects inside of one program will try to communicate with each other automatically. If a programmer wants to stop objects from interacting with each other, they need to be encapsulated in individual classes. Through the process of encapsulation, classes cannot change or interact with the specific variables and functions of an object.

Just like a pill "encapsulates" or contains the medication inside of its coating, the principle of encapsulation works in a digital way to form a protective barrier around the information that separates it from the rest of the code. Programmers can replicate this object throughout different parts of the program or other programs.

Abstraction
Abstraction is like an extension of encapsulation because it hides certain properties and methods from the outside code to make the interface of the objects simpler. Programmers use abstraction for several beneficial reasons. Overall, abstraction helps isolate the impact of changes made to the code so that if something goes wrong, the change will only affect the variables shown and not the outside code.

Inheritance
Using this concept, programmers can extend the functionality of the code's existing classes to eliminate repetitive code. For instance, elements of HTML code that include a text box, select field and check box have certain properties in common with specific methods.

Instead of redefining the properties and methods for every type of HTML element, you can define them once in a generic object. Naming that object something like "HTMLElement" will cause other objects to inherit its properties and methods so you can reduce unnecessary code.

The main object is the superclass and all objects that follow it are subclasses. Subclasses can have separate elements while adding what they need from the superclass.

Polymorphism
This technique meaning "many forms or shapes" allows programmers to render multiple HTML elements depending on the type of object. This concept allows programmers to redefine the way something works by changing how it is done or by changing the parts in which it is done. Terms of polymorphism are called overriding and overloading.

Example of encapsulation
Beginning programmers may better understand this concept in relation to how a browser functions. Browsers have local storage objects that allow you to store data locally. These objects have properties, like length, which turns the number of objects into storage, along with methods like (remove item) and (set item).

Another way to consider encapsulation is in terms of an employee's pay. The properties of an employee can include base salary, overtime and rate with a method called factor wage. Code written in an encapsulated, object-oriented way functions with fewer and fewer parameters. The fewer the number of parameters, the easier it is to use and maintain that function.

Example of abstraction
Think of a stereo system as an object with a complex logic board on the inside. It has buttons on the outside to allow for interaction with the object. When you press any of the buttons, you're not thinking about what happens on the inside because you can't see it. Even though you can't see the logic board completing functions as a result of pressing a button, it's still performing actions. This is an abstraction, which can be used to understand the concept in programming.

Another way to understand this is to consider the human body. The skin acts as an abstraction to hide the internal body parts responsible for bodily functions like digesting and walking.

Example of inheritance
Consider two classes. One is the superclass (parent) while the subclass (child) will inherit the properties of the parent class and modify its behavior. Programmers applying the technique of inheritance arrange these classes into a hierarchy of "is-a-type-of" relationships.

For instance, in the animal world, an insect would be a superclass. All insects share similar properties, such as having six legs and an exoskeleton. Grasshoppers and ants are both insects and inherited similar properties.

Example of polymorphism
To better understand the two terms of polymorphism called overloading and overriding, it helps to visualize the process of walking. Babies learn to crawl first by using their arms and legs. Once they learn to stand and walk, they are ultimately changing the body part used to accomplish the act of walking. This term of polymorphism is called overloading.

To understand the next term of overriding, think of how you naturally walk in the direction you are facing. When you stop and walk backward, this changes the direction of your path and also the mechanism of function. You are overriding the natural action that you usually complete.

#### What is method overloading?

If a class has multiple methods having same name but different in parameters, it is known as Method Overloading.

If we have to perform only one operation, having same name of the methods increases the readability of the program.

Suppose you have to perform addition of the given numbers but there can be any number of arguments, if you write the method such as a(int,int) for two parameters, and b(int,int,int) for three parameters then it may be difficult for you as well as other programmers to understand the behavior of the method because its name differs.

So, we perform method overloading to figure out the program quickly.

Advantage of method overloading:
Method overloading increases the readability of the program.

Different ways to overload the method
There are two ways to overload the method in java:

By changing number of arguments
By changing the data type

#### What is method overriding?

If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java.

In other words, If a subclass provides the specific implementation of the method that has been declared by one of its parent class, it is known as method overriding.

Usage of Java Method Overriding
Method overriding is used to provide the specific implementation of a method which is already provided by its superclass.
Method overriding is used for runtime polymorphism

Rules for Java Method Overriding
The method must have the same name as in the parent class
The method must have the same parameter as in the parent class.
There must be an IS-A relationship (inheritance).

#### Explain how object oriented languages attempt to simplify memory management for Programmers.

Programs are implemented as a sequence of operations acting upon data structures. In traditional programming the data structures would be superimposed onto an arbitrary piece of memory requested by the programmer. They would only be loosely associated with the code which operated on them. In object oriented programming languages the instantiation of an object results in a reference to the object rather than a set of addresses of where the object is stored. Instantiation ensures that exactly the correct amount of memory is allocated without the programmer having to explicitly state it. The object reference can then be associated with the methods which belong to the object class i.e. code cannot be coerced to operate on inappropriate items. As the programmer modifies the object during maintenance and testing there is no need to adjust pointer offsets etc the compiler can work out how to modify the references to storage in line with any redefinition of the class. When the object is no longer needed the memory management system which supports the OO language ensures that only memory which is no longer necessary is made available for future use. Where languages use garbage collection this is an automatic process. Where for efficiency reasons garbage collection is not used the programmer initiates the reuse of memory but the system manages exactly which locations are returned to the heap.

#### Explain the “Single Responsibility” principle!

The single-responsibility principle is a computer-programming principle that states that every module or class should have responsibility over a single part of the functionality provided by the software, and that responsibility should be entirely encapsulated by the class, module or function

#### What is an object oriented program? Explain, show.

Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which can contain data, in the form of fields (often known as attributes or properties), and code, in the form of procedures (often known as methods).

#### How do you make a class immutable? What do you need to watch out for?

To create an immutable class in Java, you have to do the following steps.

Declare the class as final so it can’t be extended.
Make all fields private so that direct access is not allowed.
Don’t provide setter methods for variables.
Make all mutable fields final so that its value can be assigned only once.
Initialize all the fields via a constructor performing deep copy.
Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

#### How many instances can be created for an abstract class?

None

## Programming languages

### Java

#### What is autoboxing and unboxing?

Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. For example, converting an int to an Integer, a double to a Double, and so on. If the conversion goes the other way, this is called unboxing.

#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?

Int

#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?

Instance Variables
A variable which is declared inside a class and outside all the methods and blocks is an instance variable. The general scope of an instance variable is throughout the class except in static methods. The lifetime of an instance variable is until the object stays in memory.

Class Variables
A variable which is declared inside a class, outside all the blocks and is marked static is known as a class variable. The general scope of a class variable is throughout the class and the lifetime of a class variable is until the end of the program or as long as the class is loaded in memory.

Local Variables
All other variables which are not instance and class variables are treated as local variables including the parameters in a method. Scope of a local variable is within the block in which it is declared and the lifetime of a local variable is until the control leaves the block in which it is declared.

#### What is the purpose of the ‘equals()’ method?

The equals() method compares two objects for equality and returns true if they are equal. The equals() method provided in the Object class uses the identity operator ( == ) to determine whether two objects are equal. For primitive data types, this gives the correct result

#### What is the difference between '==' and 'equals()'?

equals() method for content comparison. In simple words, == checks if both objects point to the same memory location whereas . equals() evaluates to the comparison of values in the objects.

#### What does the ‘static’ keyword mean?

In Java, static is a keyword used to describe how objects are managed in memory. It means that the static object belongs specifically to the class, instead of instances of that class.

#### Why is the main() method declared as static? Explain.

Java main() method is always static, so that compiler can call it without the creation of an object or before the creation of an object of the class. In any Java program, the main() method is the starting point from where compiler starts program execution. So, the compiler needs to call the main() method.

#### What is the default access modifier in a class?

When no access modifier is specified for a class , method or data member – It is said to be having the default access modifier by default.
The data members, class or methods which are not declared using any access modifiers i.e. having default access modifier are accessible only within the same package.

#### What is the JVM?

A Java virtual machine is a virtual machine that enables a computer to run Java programs as well as programs written in other languages that are also compiled to Java bytecode. The JVM is detailed by a specification that formally describes what is required in a JVM implementation.

#### What is the difference between the JRE and the JDK?

The JRE is the Java Runtime Environment. It is a package of everything necessary to run a compiled Java program, including the Java Virtual Machine (JVM), the Java Class Library, the java command, and other infrastructure. However, it cannot be used to create new programs.

The JDK is the Java Development Kit, the full-featured SDK for Java. It has everything the JRE has, but also the compiler (javac) and tools (like javadoc and jdb). It is capable of creating and compiling programs.

Usually, if you only care about running Java programs on computer you will only install the JRE. It's all you need. On the other hand, if you are planning to do some Java programming, you need to install the JDK instead.

Sometimes, even if you are not planning to do any Java development on a computer, you still need the JDK installed. For example, if you are deploying a web application with JSP, you are technically just running Java programs inside the application server. Why would you need the JDK then? Because the application server will convert JSP into Java servlets and needs to use the JDK to compile the servlets. 

#### What is the difference between long and Long?

Long is the object orientated counter part of long. The difference is as follows, and it applies to Float to float, Integer to integer etc. long is a primitive type, while Long is a Java class (and so it will inherit Object)

#### Can a long store bigger numbers than a Long?



#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.

 Contains utility classes which implement data structures like Linked List, Dictionary and support ; for Date / Time operations; 
 
AbstractCollection: This class provides a skeletal implementation of the Collection interface, to minimize the effort required to implement this interface.
AbstractList: This class provides a skeletal implementation of the List interface to minimize the effort required to implement this interface backed by a “random access” data store (such as an array).
AbstractMap<K,V>: This class provides a skeletal implementation of the Map interface, to minimize the effort required to implement this interface.
AbstractMap.SimpleEntry<K,V>: An Entry maintaining a key and a value.
AbstractMap.SimpleImmutableEntry<K,V>: An Entry maintaining an immutable key and value.
AbstractQueue: This class provides skeletal implementations of some Queue operations.
AbstractSequentialList: This class provides a skeletal implementation of the List interface to minimize the effort required to implement this interface backed by a “sequential access” data store (such as a linked list).
AbstractSet: This class provides a skeletal implementation of the Set interface to minimize the effort required to implement this interface.
ArrayDeque: Resizable-array implementation of the Deque interface.
ArrayList: Resizable-array implementation of the List interface.
Arrays: This class contains various methods for manipulating arrays (such as sorting and searching).
BitSet: This class implements a vector of bits that grows as needed.
Calendar: The Calendar class is an abstract class that provides methods for converting between a specific instant in time and a set of calendar fields such as YEAR, MONTH, DAY_OF_MONTH, HOUR, and so on, and for manipulating the calendar fields, such as getting the date of the next week.
Collections: This class consists exclusively of static methods that operate on or return collections.
Currency: Represents a currency.
Date: The class Date represents a specific instant in time, with millisecond precision.
Dictionary<K,V>: The Dictionary class is the abstract parent of any class, such as Hashtable, which maps keys to values.
EnumMap,V>: A specialized Map implementation for use with enum type keys.
EnumSet: A specialized Set implementation for use with enum types.
EventListenerProxy: An abstract wrapper class for an EventListener class which associates a set of additional parameters with the listener.
EventObject: The root class from which all event state objects shall be derived.
FormattableFlags: FomattableFlags are passed to the Formattable.formatTo() method and modify the output format for Formattables.
Formatter: An interpreter for printf-style format strings.
GregorianCalendar: GregorianCalendar is a concrete subclass of Calendar and provides the standard calendar system used by most of the world.
HashMap<K,V>: Hash table based implementation of the Map interface.
HashSet: This class implements the Set interface, backed by a hash table (actually a HashMap instance).
Hashtable<K,V>: This class implements a hash table, which maps keys to values.
IdentityHashMap<K,V>: This class implements the Map interface with a hash table, using reference-equality in place of object-equality when comparing keys (and values).
LinkedHashMap<K,V>: Hash table and linked list implementation of the Map interface, with predictable iteration order.
LinkedHashSet: Hash table and linked list implementation of the Set interface, with predictable iteration order.
LinkedList: Doubly-linked list implementation of the List and Deque interfaces.
ListResourceBundle: ListResourceBundle is an abstract subclass of ResourceBundle that manages resources for a locale in a convenient and easy to use list.
Locale – Set 1, Set 2: A Locale object represents a specific geographical, political, or cultural region.
Locale.Builder: Builder is used to build instances of Locale from values configured by the setters.
Objects: This class consists of static utility methods for operating on objects.
Observable: This class represents an observable object, or “data” in the model-view paradigm.
PriorityQueue: An unbounded priority queue based on a priority heap.
Properties: The Properties class represents a persistent set of properties.
PropertyPermission: This class is for property permissions.
PropertyResourceBundle: PropertyResourceBundle is a concrete subclass of ResourceBundle that manages resources for a locale using a set of static strings from a property file.
Random: An instance of this class is used to generate a stream of pseudorandom numbers.
ResourceBundle: Resource bundles contain locale-specific objects.
ResourceBundle.Control: ResourceBundle.Control defines a set of callback methods that are invoked by the ResourceBundle.getBundle factory methods during the bundle loading process.
Scanner: A simple text scanner which can parse primitive types and strings using regular expressions.
ServiceLoader: A simple service-provider loading facility.
SimpleTimeZone: SimpleTimeZone is a concrete subclass of TimeZone that represents a time zone for use with a Gregorian calendar.
Stack: The Stack class represents a last-in-first-out (LIFO) stack of objects.
StringTokenizer: The string tokenizer class allows an application to break a string into tokens.
Timer: A facility for threads to schedule tasks for future execution in a background thread.
TimerTask: A task that can be scheduled for one-time or repeated execution by a Timer.
TimeZone: TimeZone represents a time zone offset, and also figures out daylight savings.
TreeMap<K,V>: A Red-Black tree based NavigableMap implementation.
TreeSet: A NavigableSet implementation based on a TreeMap.
UUID: A class that represents an immutable universally unique identifier (UUID).
Vector: The Vector class implements a growable array of objects.
WeakHashMap<K,V>: Hash table based implementation of the Map interface, with weak keys.

#### What are the access modifiers in Java? Which one could we use for class?

Java provides 4 levels of access modifiers. This means that you can modify access to a variable, method or a class in 4 ways. These 4 ways are private, public, protected and default.

By default, classes can only have 2 modifiers:

public
no modifier (default modifier)

#### Can an “enum” contain methods in Java? Explain.

The enum class body can include methods and other fields. The compiler automatically adds some special methods when it creates an enum. For example, they have a static values method that returns an array containing all of the values of the enum in the order they are declared.

#### When would you use a private/protected/public attribute? What is the difference?

public scope to make that property/method available from anywhere, other classes and instances of the object.

private scope when you want your property/method to be visible in its own class only.

protected scope when you want to make your property/method visible in all classes that extend current class including the parent class.

#### How do you prevent developers from subclassing a class?

You can prevent a class from being subclassed by using the final keyword in the class's declaration. Similarly, you can prevent a method from being overridden by subclasses by declaring it as a final method. 

#### How do you prevent developers from overriding a method in a subclass?

By specifying final keyword to the method you can avoid overriding in a subcalss. Similarlly one can use final at class level to prevent creating subclasses.

#### How do you prevent developers from changing the value of a variable?

To prevent changing the value inside an object you can mark the fields as final . A final keyword in declaration of object instance means the variable can't be reassigned and doesn't guarantee that the object state won't change if the reference to that object is shared.

#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!

Java has Currency class that represents the ISO 4217 currency codes. BigDecimal is the best type for representing currency decimal values.

#### What happens if you try to call something, that you have no access to, because of data hiding?

#### What happens if you try to delete/drop an item from an array, while you are iterating over it?

Even though java. util. ArrayList provides the remove() methods, e.g. remove (int index) and remove (Object element), you cannot use them to remove items while iterating over ArrayList in Java because they will throw ConcurrentModificationException if called during iteration.

#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?

Even though java. util. ArrayList provides the remove() methods, e.g. remove (int index) and remove (Object element), you cannot use them to remove items while iterating over ArrayList in Java because they will throw ConcurrentModificationException if called during iteration.

#### What happens if you try to add an item to the end of an array, while you are iterating over it?

#### If you need to access the iterator variable after a for loop, how would you do it?

#### Which interfaces extend the Collection interface in Java. Which classes?

Java Collection framework provides interfaces and class implementations that enable data handling simple and meaningful. The Collection Interface resides at the top of the Hierarchy, although Java does not provides a direct implementation of Collection framework but Collection Interface is being implemented by List and Set Classes. The following list describes the core collection interfaces:

Collection - Collection is the root of the collection hierarchy.

List — The List interface extends the Collection interface to maintain a sequence of elements that need not be unique.

Set — The Set interface extends the Collection interface and contains a set of unique elements.

SortedSet — The SortedSet interface extends the Set interface to provide the required functionality for maintaining a set in which the elements are stored in some sorted order.

Queue — A collection used to hold multiple elements prior to processing.

Deque — a collection used to hold multiple elements prior to processing. Besides basic Collection operations, a Deque provides additional insertion, extraction, and inspection operations

Map — an object that maps keys to values.

SortedMap : Extends the Map interface for maps that maintain their mappings sorted in key order.

#### What is the connection between equals() and hashCode()? How are they used in HashMap?

It is possible to provide your own implementation of hashCode(). In HashMap, hashCode() is used to calculate the bucket and therefore calculate the index. equals method is used to check that 2 objects are equal or not. This method is provided by Object class.

#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?


1. What is an exception in Java?
“An exception is an unexpected event that occurs during the execution of a program that disrupts the normal flow of instructions.”

In Java, all errors and exceptions are represented with Throwable class. When an error occurs within a method, the method creates an object (of any subtype of Throwable) and hands it off to the runtime system. The object, called an exception object.

Exception object contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.

1.1. Exception handling
We have two choices when an exception object is created in our application.

Either we will handle it within method
Or we can pass it to the caller method to let it handle.
This is very important decision to be made while setting the responsibilities of a method. A method should clearly indicate that what all exceptional scenarios it will handle and which it will not. It is defined in method syntax using throws clause.

To handle the exception, We must catch the exception in catch section of try-catch block.

If an exception is not handled in the application, then it will propagate to JVM and JVM will usually terminate the program itself.


2. Checked vs unchecked exceptions in Java
2.1. Exception Hierarchy
In Java, exceptions are broadly categorized into two sections: checked exceptions and unchecked exceptions.

ExceptionHierarchyJava

2.2. Checked Exceptions
Java forces you to handle these error scenarios in some manner in your application code. They will come immediately into your face, once you start compiling your program. You can definitely ignore them and let them pass to JVM, but it’s bad habit. Ideally, you must handle these exceptions at suitable level inside your application so that you can inform the user about failure and ask him to retry/ come later.

Generally, checked exceptions denote error scenarios which are outside the immediate control of the program. They occur usually interacting with outside resources/network resources e.g. database problems, network connection errors, missing files etc.

Checked exceptions are subclasses of Exception class.

Example of checked exceptions are : ClassNotFoundException, IOException, SQLException and so on.

Checked Exception Example
FileNotFoundException is a checked exception in Java. Anytime, we want to read a file from filesystem, Java forces us to handle error situation where file may not be present in place.

Try to read file with handle FileNotFoundException
public static void main(String[] args) 
{
    FileReader file = new FileReader("somefile.txt");
}
In above case, you will get compile time error with message – Unhandled exception type FileNotFoundException.

To make program able to compile, you must handle this error situation in try-catch block. Below given code will compile absolutely fine.

Try to read file with exception handling
public static void main(String[] args) 
{
    try
    {
        FileReader file = new FileReader("somefile.txt");
    } 
    catch (FileNotFoundException e) 
    {
        //Alternate logic
        e.printStackTrace();
    }
}
2.3. Unchecked Exceptions
Java also provides UncheckedExceptions, the occurrences of which are not checked by the compiler. They will come into life/occur into your program, once any buggy code is executed.

A method is not forced by compiler to declare the unchecked exceptions thrown by its implementation. Generally, such methods almost always do not declare them, as well.

Unchecked Exceptions are subclasses of RuntimeException. Example of unchecked exceptions are : ArithmeticException, ArrayStoreException, ClassCastException and so on.

“The strange thing is that RuntimeException is itself subclass of Exception i.e. all unchecked exception classes should have been checked exceptions implicitly, BUT they are not.”
Unchecked Exception Example
Checkout the given code below. Above code does not give any compile time error. But when you the example, it throws NullPointerException. NullPointerException is unchecked exception in Java.

JVM not forcing you to check NullPointerException
public static void main(String[] args) 
{
    try
    {
        FileReader file = new FileReader("pom.xml");
         
        file = null;
         
        file.read();
    } 
    catch (IOException e) 
    {
        //Alternate logic
        e.printStackTrace();
    }
}
Remember the biggest difference between checked and unchecked exceptions is that checked exceptions are forced by compiler and used to indicate exceptional conditions that are out of the control of the program (for example, I/O errors), while unchecked exceptions are occurred during runtime and used to indicate programming errors (for example, a null pointer).


#### What is Error in Java and how does it relate to Exception?

An Error “indicates serious problems that a reasonable application should not try to catch.”
Both Errors and Exceptions are the subclasses of java.lang.Throwable class. Errors are the conditions which cannot get recovered by any handling techniques. It surely cause termination of the program abnormally. Errors belong to unchecked type and mostly occur at runtime. Some of the examples of errors are Out of memory error or a System crash error.

#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?

Java finally block is a block that is used to execute important code such as closing connection, stream etc.

Java finally block is always executed whether exception is handled or not.

Java finally block follows try or catch block.

#### What is the largest number you can work with in Java?

#### When you use method overriding, can you change the access level of the method, from protected to public? Why?When you use method overriding, can you change the access level of the method, from public to protected? Why?

#### Can the main method be overridden? Explain your answer!
#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?
#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?
#### What does "final" mean in case of a variable, method or a class?
#### What is the super keyword?
#### What are “generics”? When to use? Show examples.
#### What is the benefit of having “generic” containers?
#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
#### What is an annotation? What can be annotated and how? Show examples.

### Database

#### How can you connect your application to a database server? What are the possible ways?
#### What do you know about database normalization?
