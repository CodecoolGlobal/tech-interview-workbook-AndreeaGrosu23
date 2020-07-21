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



#### Define the following terms: Instantiation, Attribute, Method
#### Could we access a static variable (or method) from a non-static method? Why?
#### Could we access a non-static variable (or method) from a static method? Why?
#### How many instances you have of a static variable of a given class?
#### Why is it not a good practice to write a lot of static methods?
#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
#### What is the ‘this’ reference?
#### What are base class, subclass and superclass?
#### Draw an object oriented family (as entities, with relations) on the whiteboard.
#### Difference between overloading and overriding?
#### What are the Object Oriented Principles? Explain the concepts with realistic examples!
#### What is method overloading?
#### What is method overriding?
#### Explain how object oriented languages attempt to simplify memory management for Programmers.
#### Explain the “Single Responsibility” principle!
#### What is an object oriented program? Explain, show.
#### How do you make a class immutable? What do you need to watch out for?
#### How many instances can be created for an abstract class?

## Programming languages

### Java

#### What is autoboxing and unboxing?
#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?
#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?
#### What is the purpose of the ‘equals()’ method?
#### What is the difference between '==' and 'equals()'?
#### What does the ‘static’ keyword mean?
#### Why is the main() method declared as static? Explain.
#### What is the default access modifier in a class?
#### What is the JVM?
#### What is the difference between the JRE and the JDK?
#### What is the difference between long and Long?
#### Can a long store bigger numbers than a Long?
#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.
#### What are the access modifiers in Java? Which one could we use for class?
#### Can an “enum” contain methods in Java? Explain.
#### When would you use a private/protected/public attribute? What is the difference?
#### How do you prevent developers from subclassing a class?
#### How do you prevent developers from overriding a method in a subclass?
#### How do you prevent developers from changing the value of a variable?
#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!
#### What happens if you try to call something, that you have no access to, because of data hiding?
#### What happens if you try to delete/drop an item from an array, while you are iterating over it?
#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?
#### What happens if you try to add an item to the end of an array, while you are iterating over it?
#### If you need to access the iterator variable after a for loop, how would you do it?
#### Which interfaces extend the Collection interface in Java. Which classes?
#### What is the connection between equals() and hashCode()? How are they used in HashMap?
#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?
#### What is Error in Java and how does it relate to Exception?
#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?
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

### C&#35;

#### Explain the purpose of IL and how does it relate to CLR?
#### What does “managed code” mean?
#### What is an assembly?
#### What is the difference between an EXE and a DLL?
#### What is strong-typing versus weak-typing? Which is preferred? Why?
#### What is a namespace?
#### Explain sealed class in C#?
#### What is explicit vs. implicit conversion? Give examples of both of them.
#### Is a struct stored on the heap or stack?
#### Can a struct have methods?
#### Can DateTimes be null?
#### List out the differences between Array and ArrayList in C#?
#### How is the using() pattern useful? What is IDisposable? How does it support deterministic finalization?
#### How can you make sure that objects using dedicated resources (database connection, files, hardware, OS handle, etc.) are released as early as possible?
#### Why to use keyword “const” in C#? Give an example.
#### What is the difference between “const” and “readonly” variables in C#?
#### What is a property in C#?
#### List out two different types of errors in C#?
#### What is the difference between “out” and “ref” parameters in C#?
#### Can we override private virtual method in C#?
#### What's the difference between IEquatable and just overriding Object.Equals()?
#### Explain the differences between public, protected, private and internal. Explain access modifier – “protected internal” in C#!
#### What’s the difference between using `override` and `new` keywords when defining method in child class?
#### Explain StringBuilder class in C#!
#### How we can sort the array elements in descending order in C#?
#### Can you use a value type as a generic type argument in C#? For example when implementing an interface like (IEquatable).
#### What are Nullable Types in C#?
#### Conceptually, what is the difference between early-binding and late-binding?
#### What is delegate, event, callback, multicast delegate?
#### What is enum in C#?
#### What is null-conditional operator?
#### What is null-coalescing operator?
#### What is serialization?
#### What is the difference between Finalize() and Dispose() methods?
#### How do you inherit a class from another class in C#?
#### What is difference between “is” and “as” operators in C#?
#### What are indexers in C# .NET?
#### What is the difference between returning IQueryable<T> vs. IEnumerable<T>?
#### What is LINQ? Explain the idea of extension methods.
#### What are the advantages and disadvantages of lazy loading?
#### How to use of “yield” keyword? Mention at least one practical scenario where it can be used?
#### What are attributes in C#? Give some examples of usage of them.
#### By what mechanism does NUnit know what methods to test?
#### What is the GAC? What problem does it solve?
#### What is the largest number you can work with in C#?

### Database

#### How can you connect your application to a database server? What are the possible ways?
#### What do you know about database normalization?
