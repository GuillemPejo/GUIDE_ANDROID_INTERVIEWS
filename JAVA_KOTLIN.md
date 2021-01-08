## JAVA
#### Object-Oriented Programming
* What are the main 3 Object Oriented Programing (OOP) concepts?
* Explain object serialization and how to implement it in Java.
* Explain anonymous classes. [[info]](http://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html)
* Describe the differences between abstract classes and interfaces. [[info]](http://www.javaworld.com/article/2077421/learn-java/abstract-classes-vs-interfaces.html)
* Explain what a Singleton class is and how to create one in Java [[info]](http://www.javaworld.com/article/2073352/core-java/simply-singleton.html)
* Why should the equals() and hashCode() methods often be overridden together? [[info]](http://stackoverflow.com/questions/2265503/why-do-i-need-to-override-the-equals-and-hashcode-methods-in-java/2265637#2265637)
* How do you properly override the equals() method? For example, what considerations should be taken when checking for equality? [[info]](http://www.geeksforgeeks.org/overriding-equals-method-in-java/)
* Difference between final, finally and finalize?
* In Java, does the finally block gets executed if we insert a return statement inside the try block of a try-catch-finally?  [[info]](https://stackoverflow.com/a/65049/497132)
* Explain method overloading & overriding. 
* What is memory leak and how does Java handle it? [[info]](https://stackify.com/memory-leaks-java/)

#### Data Structures
* What are the use cases and differences of arrays and ArrayLists?
* What are the use cases and differences of a HashSet and a TreeSet?  [[info]](https://stackoverflow.com/a/4464394/497132)

#### Build Tools
* Have you used any Ant, Maven, Gradle features for your project?

#### Programming Paradigms
* Explain event-driven programming in Java [[info]](http://en.wikibooks.org/wiki/Java\_Programming/Event\_Handling)
* What is Java's Garbage Collection and how does it help you as a developer?
* How can you typecast in Java? [[info]](http://www.studytonight.com/java/type-casting-in-java)
* Explain Java's try-catch-finally paradigm [[info]](http://www.studytonight.com/java/try-and-catch-block.php)



### Java and Kotlin
 
  
### Java Interview Questions  
* <b>Why is Java said to be platform independent?</b></br>
   * The execution of the code does not depend upon the OS</br>
   
   
* <b>Difference between ‘throw’ and ‘throws’ in Java Exception Handling?</b></br>
   * ```throw``` keyword is used to throw Exception from any method or static block whereas ```throws``` is used to indicate that which Exception can possibly be thrown by this method.</br>
   
   
* <b>Is there ever a scenario where we can skip the finally block in a try catch?</b></br>
   * By Calling System.exit(0) in try or catch block, we can skip the finally block. System.exit(int) method can throw a SecurityException. If System.exit(0) exits the JVM without throwing that exception then finally block will not execute. But, if System.exit(0) does throw security exception then finally block will be executed.</br>
   
   
* <b>What are anonymous classes?</b></br>
   * An anonymous class is just what its name implies -- it has no name. It combines the class declaration and the creation of an instance of the class in one step. Since anonymous classes have no name, objects can not be instantiated from outside the class in which the anonymous class is defined. In fact, an anonymous object can only be instantiated from within the same scope in which it is defined.
   * Rules:
      * An anonymous class must always extend a super class or implement an interface but it cannot have an explicit extends or implements clause.
      * An anonymous class must implement all the abstract methods in the super class or the interface.
      * An anonymous class always uses the default constructor from the super class to create an instance.
      * Example: 
      ``` 
      MyButton.setOnClickListener(new Button.OnClickListener {
             @override
                public void onClick(View view){
                    //some code
                }
         });
 </br>
      
      
* <b>Why is the main method static in java?</b></br>
   * The method is static because otherwise there would be ambiguity on which method to be called. If static is removed from the main method, Program compiles successfully . But at runtime throws an error “NoSuchMethodError”.
   * We can overload the main method in Java. But the program doesn’t execute the overloaded main method when we run your program, we need to call the overloaded main method from the actual main method only. To run a method without calling this main method, we would need to execute a static block.
   * In order to avoid NoSuchMethodError, we can call System.exit(0) after the static method.
   * Note: Any method declared static will be executed even before the main class is executed.
   * Example:
   ```
   public class Hello { 
       static { 
        System.out.println("Hello, World!"); 
       } 
     }
     ```
   </br>
   
      
* <b>What is garbage collector? How does it work?</b></br>
   * All objects are allocated on the heap area managed by the JVM. As long as an object is being referenced, the JVM considers it alive. Once an object is no longer referenced and therefore is not reachable by the application code, the garbage collector removes it and reclaims the unused memory.</br>
   
   
* <b>Difference between stack memory & heap memory?</b></br>
   * Stack is used for static memory allocation and Heap for dynamic memory allocation, both stored in the computer's RAM .
   * Variables allocated on the stack are stored directly to the memory and access to this memory is very fast, and it's allocation is dealt with when the program is compiled. When a function or a method calls another function which in turns calls another function etc., the execution of all those functions remains suspended until the very last function returns its value. The stack is always reserved in a LIFO order, the most recently reserved block is always the next block to be freed. This makes it really simple to keep track of the stack, freeing a block from the stack is nothing more than adjusting one pointer.
   * Variables allocated on the heap have their memory allocated at run time and accessing this memory is a bit slower, but the heap size is only limited by the size of virtual memory . Element of the heap have no dependencies with each other and can always be accessed randomly at any time. You can allocate a block at any time and free it at any time. This makes it much more complex to keep track of which parts of the heap are allocated or free at any given time.
   * You can use the stack if you know exactly how much data you need to allocate before compile time and it is not too big. You can use heap if you don't know exactly how much data you will need at runtime or if you need to allocate a lot of data.
   * In a multi-threaded situation each thread will have its own completely independent stack but they will share the heap. Stack is thread specific and Heap is application specific. The stack is important to consider in exception handling and thread executions.
       * Heap memory is used by all the parts of the application whereas stack memory is used only by one thread of execution.
       * Whenever an object is created, it’s always stored in the Heap space and stack memory contains the reference to it. Stack memory only contains local primitive variables and reference variables to objects in heap space.
       * Objects stored in the heap are globally accessible whereas stack memory can’t be accessed by other threads.
       * Memory management in stack is done in LIFO manner whereas it’s more complex in Heap memory because it’s used globally. Heap memory is divided into Young-Generation, Old-Generation etc, more details at Java Garbage Collection.
       * Stack memory is short-lived whereas heap memory lives from the start till the end of application execution.
       * When stack memory is full, Java runtime throws java.lang.StackOverFlowError whereas if heap memory is full, it throws java.lang.OutOfMemoryError: Java Heap Space error.
       * Stack memory size is very less when compared to Heap memory. Because of simplicity in memory allocation (LIFO), stack memory is very fast when compared to heap memory.</br>   
   
   
* <b>Explain OOPs concept</b></br>
   * Object Oriented Programming is a programming style that involves concepts such as Classes, objects,<b>Abstraction</b>, <b>Encapsulation</b>, <b>Inheritance</b>, <b>Polymorphism</b>.</br>
   
   
* <b>What is Inheritance?</b></br>
   * Inheritance is the process by which objects of one class acquire the properties & objects of another class. The two most common reasons to use inheritance are: a) To promote code reuse. b) To use polymorphism.</br>
   
   
* <b>Does Java support multiple inheritance?</b></br>
   * Java supports multiple inheritance by interface only since it can implement multiple interfaces but can extend only one class.</br>
   
   
* <b>What is Encapsulation?</b></br>
   * Encapsulation involves binding code and data together as a single unit. 
   * Encapsulation is a technique used for hiding the properties and behaviors of an object and allowing outside access only as appropriate. It prevents other objects from directly altering or accessing the properties or methods of the encapsulated object. 
   * For instance, a class can be an encapsulated class if all the variables in it are defined as Private and by providing getter and setter methods.
</br>


* <b>What is Abstract class?</b></br>
   * Abstract classes are classes that contain one or more abstract methods. An abstract method is a method that is declared, but contains no implementation. 
   * If even a single method is abstract, the whole class must be declared abstract.
   * Abstract classes may not be instantiated, and require subclasses to provide implementations for the abstract methods.
   * You can’t mark a class as both abstract and final.
   * Non-abstract methods can access a method that you declare as abstract.</br>
   
   
* <b>What are Interfaces?</b></br>
   * Interfaces are only declared methods that an implementing class would need. 
   * Interfaces cannot be marked as final. Interface variables must be static or final. 
   * Interfaces cannot be instantiated directly.
   * <b>Marker Interfaces</b>: Marker interfaces are those which do not declare any required Methods. The java.io.Serializable interface is a typical marker interfaces. These do not contain any methods, but classes must implement this interface in order to be serialized and de-serialized.</br>
   
   
* <b>Difference between Abstract and Interfaces?</b></br>
   * Abstract classes can have non abstract methods. It can have instance variables. We have provide default implementation to abstract class method. A class can extend only one abstract class.A class can implement multiple interfaces.</br>
  <a href="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/1.png" target="_blank"><img src="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/1.png"></a>
</br>   


* <b>What is Polymorphism?</b></br>
   * Polymorphism is when an object takes on multiple forms. For instance, String is a subclass of Object class. 
   * Polymorphism manifests itself in Java in the form of multiple methods having the same name.
   * In some cases, multiple methods have the same name, but different formal argument lists (overloaded methods).
   * In other cases, multiple methods have the same name, same return type, and same formal argument list (overridden methods).
   * Polymorphism is a characteristic of being able to assign a different meaning or usage to something in different contexts - specifically, to allow an entity such as a variable, a function, or an object to have more than one form.
   * 2 forms of polymorphism:  
       * Compile time polymorphism: The flow of control is decided during the compile time itself. By overloading.
       * Run time polymorphism: is done using inheritance and interface. The flow of control is decided during the runtime. Overriding: Overriding will have the same method name with the same parameters. One will be the parent class method and the other will be the child class method. Overloading occurs when the same method name is declared but with different parameters.</br>
       
       
* <b>What is Method overloading?</b></br>
   * Method Overloading means to have two or more methods with same name in the same class with different arguments. 
   * Note:
     * Overloaded methods MUST change the argument list
     * Overloaded methods CAN change the return type
     * Overloaded methods CAN change the access modifier
     * Overloaded methods CAN declare new or broader checked exceptions
     * A method can be overloaded in the same class or in a subclass </br>
     
     
* <b>What is Method overriding?</b></br>
   * Method overriding occurs when sub class declares a method that has the same type arguments as a method declared by one of its superclass
   * You can’t override a method marked public and make it protected
   * You cannot override a method marked final
   * You cannot override a method marked static
   * Note: Static methods cannot be overridden. Overloaded methods can still be overridden. </br>
   
   
* <b>Why would you not call abstract method in constructor?</b></br>
   * The problem is that the class is not yet fully initialized, and when the method is called in a subclass, it may cause trouble.</br>
   

* <b>Composition over inheritance?</b></br>
   * Composition is typically "has a" or "uses a" relationship. In the below example, the Employee class has a Person. It does not inherit from Person but instead gets the Person object passed to it, which is why it is a "has a" Person.
```
class Person {
   String Title;
   String Name;
   Int Age;

   public Person(String title, String name, String age) {
      this.Title = title;
      this.Name = name;
      this.Age = age;
   }

}

class Employee {
   Int Salary;
   private Person person;

   public Employee(Person p, Int salary) {
       this.person = p;
       this.Salary = salary;
   }
}
```
</br>
      
      
* <b>Difference between Encapsulation & Abstraction?</b></br>
   * <b>Abstraction</b> focuses on the outside view of an object (i.e. the interface) 
   * <b>Encapsulation</b> (information hiding) prevents clients from seeing it’s inside view. 
   * Abstraction solves the problem in the design side while Encapsulation is the Implementation.</br>
   
   
* <b>Constructors vs Methods?</b></br>
   * <b>Constructors</b> must have the name as the class name and does not have a return type. It can be used to instantiate any objects in the class whereas methods have no such rule and is another member of the class. Constructors cannot be inherited but a derived class can call the super constructor of parent class.
   * ```this()```: Constructors use this to refer to another constructor in the same class with a different parameter list.
   * ```super()```: Constructors use super to invoke the superclass's constructor.
   * <b>Methods</b>: Instance methods on the other hand require an instance of the class to exist before they can be called, so an instance of a class needs to be created by using the new keyword. Class methods are methods which are declared as static. The method can be called without creating an instance of the class</br>
   
   
   
* <b>What is the difference between instantiation and initialization of an object?</b></br>
   * <b>Initialization</b> is the process of the memory allocation, when a new variable is created. Variables should be explicitly given a value, otherwise they may contain a random value that remained from the previous variable that was using the same memory space. To avoid this problem, Java language assigns default values to data types.
   * <b>Instantiation</b> is the process of explicitly assigning definitive value to a declared variable.</br>
   
   
* <b>Do objects get passed by reference or value in Java? Elaborate on that.</b></br>
   * Java is always pass-by-value. When we pass the value of an object, we are passing the reference to it. 
   * Java creates a copy of the variable being passed in the method and then does the manipulations. Hence the change is not reflected in the main method.
   * But when you pass an object reference into a method, a copy of this reference is made, so it still points to the same object. This means, that any changes that you make to the insides of this object are retained, when the method exits.
   * Java copies and passes the reference by value, not the object. Thus, method manipulation will alter the objects, since the references point to the original objects. But since the references are copies, swaps will fail.</br>
   
   
* <b>Primitives in Java?</b></br>
  <a href="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/2.png" target="_blank"><img src="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/2.png"></a></br>
  
  
* <b>Difference between == and .equals() method in Java?</b></br>
   * We can use == operators for reference comparison (address comparison) and ```.equals()``` method for content comparison.    * In simple words, == checks if both objects point to the same memory location whereas .equals() evaluates to the comparison of values in the objects.</br>
   
   
* <b>Why strings are Immutable?</b></br>
   * Once a value is assigned to a string it cannot be changed. And if changed, it creates a new object of the String. This is not the case with StringBuffer.</br>
   
   
* <b>What is String.intern()? When and why should it be used?</b></br>
   * String.intern() method can be used to to deal with String duplication problem in Java. By carefully using the intern() method you can save a lot of memories consumed by duplicate String instances. A string is duplicate if it contains the same content as another string but occupied different memory location.
   * By calling  the intern() method on a string object, for instance “abc”, you can instruct JVM to put this String in the pool and whenever someone else creates "abc", this object will be returned instead of creating a new object. This way, you can save a lot of memory in Java, depending upon how many Strings are duplicated in your program.
   * When the intern method is invoked, if the String pool already contains that String object such that equals() return true, it will return the String object from the pool, otherwise it will add that object to the pool of unique String.</br>
   
   
   
* <b>String pool in Java:</b></br>
   * String Pool in java is a pool of Strings stored in Java Heap Memory. 
   * When we use double quotes to create a String, it first looks for String with same value in the String pool, if found it just returns the reference else it creates a new String in the pool and then returns the reference.
   * However using new operator, we force String class to create a new String object in heap space. We can use intern() method to put it into the pool or refer to other String object from string pool having same value.
   * For example, how many strings are getting created in below statement;
  ``` String str = new String("Cat");```
   * In above statement, either 1 or 2 string will be created. If there is already a string literal “Cat” in the pool, then only one string “str” will be created in the pool. If there is no string literal “Cat” in the pool, then it will be first created in the pool and then in the heap space, so total 2 string objects will be created.</br>
   

* <b><i>Final</i> modifier?</b></br>
   * Final modifiers - once declared cannot be modified. A blank final variable in Java is a final variable that is not initialized during declaration. 
      * final Classes- A final class cannot have subclasses.
      * final Variables- A final variable cannot be changed once it is initialized.
      * final Methods- A final method cannot be overridden by subclasses.</br>
      
      
* <b><i>Finalize</i> keyword?</b></br>
   * Finalize is a method used to perform clean up processing just before object is garbage collected.</br>
   
   
* <b><i>Finally</i> keyword?</b></br>
   * finally is a code block and is used to place important code, it will be executed whether exception is handled or not.</br>
   
   
* <b><i>Static</i> variables?</b></br>
   * Variables that have only one copy per class are known as static variables. They are not attached to a particular instance of a class but rather belong to a class as a whole.
   * A static variable is associated with the class as a whole rather than with specific instances of a class. Non-static variables take on unique values with each object instance.</br> 
   
   
* <b>What is reflection?</b></br>
   * Java Reflection makes it possible to inspect classes, interfaces, fields and methods at runtime, without knowing the names of the classes, methods etc. at compile time. It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.</br> 
   
   
* <b>Multi threading?</b></br>
   * Multiple tasks are running concurrently in a program.</br>
   
   
* <b>Fail-fast & Fail-Safe?</b></br>
   * Fail-fast Iterators throws ConcurrentModificationException when one Thread is iterating over collection object and other thread structurally modify Collection either by adding, removing or modifying objects on underlying collection. They are called fail-fast because they try to immediately throw Exception when they encounter failure. 
   * On the other hand [fail-safe](http://javarevisited.blogspot.com/2011/10/java-iterator-tutorial-example-list.html) Iterators works on copy of collection instead of original collection.</br>
   
   
* <b>What does the keyword synchronized mean?</b></br>
   * When you have two threads that are reading and writing to the same 'resource', say a variable named 'test', you need to ensure that these threads access the variable in an atomic way. Without the synchronized keyword, your thread 1 may not see the change thread 2 made to test.
   * <b>synchronized</b> blocks the next thread's call to method as long as the previous thread's execution is not finished. Threads can access this method one at a time.</br>
   
   
* <b>What does the keyword volatile mean?</b></br>
   * Suppose two threads are working on a method. If two threads run on different processors each thread may have its own local copy of variable. If one thread modifies its value the change might not reflect in the original one in the main memory instantly. 
   * Now the other thread is not aware of the modified value which leads to data inconsistency.Essentially, volatile is used to indicate that a variable's value will be modified by different threads. “volatile” tells the compiler that the value of a variable must never be cached as its value may change outside of the scope of the program itself.
   * The value of this variable will never be cached thread-locally: all reads and writes will go straight to "main memory"
   * An access to a volatile variable never has the potential to block: we're only ever doing a simple read or write, so unlike a synchronized block we will never hold on to any lock.</br>
   
   
* <b>What is Autoboxing and Unboxing?</b></br>
   * Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. For example, converting an int to an Integer, a double to a Double, and so on. If the conversion goes the other way, this is called unboxing.</br>
   
   
* <b>Optionals in Java?</b></br>
   * Optional is a container object which is used to contain not-null objects. Optional object is used to represent null with absent value. This class has various utility methods to facilitate code to handle values as ‘available’ or ‘not available’ instead of checking null values.</br>
   
   
* <b>What is externalization?</b></br>
   * In serialization, the JVM is responsible for the process of writing and reading objects. This is useful in most cases, as the programmers do not have to care about the underlying details of the serialization process.
   * However, the default serialization does not protect sensitive information such as passwords and credentials.
   * Thus externalization comes to give the programmers full control in reading and writing objects during serialization.
   * Implement the java.io.Externalizable interface - then you implement your own code to write object’s states in the ```writeExternal()``` method and read object’s states in the ```readExternal()``` method.</br>
   
   

* <b>What are Data Structures?</b></br>
   * Intentional arrangement of a collection of data. There are 5 fundamental behaviours of a data structure: access, insert, delete, find & sort.</br>
   
   
* <b>Explain Big O Notation?</b></br>
   * The notation Ο(n) is the formal way to express the upper bound of an algorithm's running time. It measures the worst case time complexity or the longest amount of time an algorithm can possibly take to complete. 
   * Note: <b>O(1)</b> means that it takes a constant time, like three minutes no matter the amount of data in the set.
<b>O(n)</b> means it takes an amount of time linear with the size of the set.</br>


* <b>Explain Big Omega Notation</b></br>
   * The Big Omega Notation is used to describe the best case running time for a given algorithm.</br>


* <b>Arrays in Java?</b></br>
   * Arrays is an ordered collection. It will have a fixed length which needs to be defined at the initialization time whereas lists have a variable length. Arrays are easier to store elements of the same data type. Used internally in stack and queue.    It is a convenient way of representing a 2D array.
   * Arrays cannot hold generic data types whereas lists can.
   * Arrays can store all data types whereas lists cannot store primitive data types, only objects.
   * Arrays: Complexity:
   
   	| Algorithm	|  Average	 | Worst Case  |
    | ---------- |:--------:| -----------:| 
    | Space	    |	  Θ(n)		  |  O(n)       |
    | Search	   |   Θ(n)	   |  O(n)       |
    | Insert	   |   Θ(n)	   |  O(n)       |
    | Delete	   |   Θ(n)		  |  O(n)       |
    
    </br>
    
    
* <b>Linked Lists in Java?</b></br>
   * A LinkedList contains both a head and a tail. The "Head" is the first item in the LinkedList, while the "Tail" is the last item. It is not a circular data structure, therefore the tail does not have its' pointer pointing at the Head - the pointer is just null.
   * No indices but each node has a pointer pointing to the next element.
   * They are dynamic in nature which means they allocate memory only when needed.
   * Insertion, deletion, updation easy
   * A linked list is a group of nodes which represent a sequence. Each node consists of a data and a link or reference to the next node in the sequence.
   * <b>Singly Linked List</b>: has a node and a pointer to the next node in the sequence. 
   * <b>Doubly Linked List</b>: has a node and 2 pointers - one to the next node and one to the previous node in the sequence. This is very convenient if you need to be able to traverse stored elements in both directions.
   * Linked List: Runtime Complexity:
   
   	| Algorithm	|  Average	 | Worst Case  |
    | ---------- |:--------:| -----------:| 
    | Space	    |	  Θ(n)		  |  O(n)       |
    | Search	   |   Θ(n)	   |  O(n)       |
    | Insert	   |   Θ(1)	   |  O(1)       |
    | Delete	   |   Θ(1)		  |  O(1)       |
    
    </br>


* <b>Binary Tree</b></br>
   * A tree whose elements have at most 2 children is called a binary tree. Since each element in a binary tree can have only 2 children, we typically name them the left and right child. 
   * The left subtree of a node contains only values less than the parent node's value. 
   * The right subtree of a node contains only values greater than or equal to the node's value.
   * Only if the above 2 criteria are matched, then the tree is said to be balanced.
   * <b>Advantages of Binary tree over Linked List</b>: In a linked list, the items are linked together through a single next pointer. In a binary tree, as long as the tree is balanced, the searchpath to each item is a lot shorter than that in a linked list.
   * Their disadvantage is that in the worst case they can degenerate into a linked list in terms of efficiency.</br>



* <b>Stacks:</b></br>
   * Stacks are an abstract collection that follow LIFO mechanism. 
   * Main functionalities include 
       * <b>Push</b>: a new entity added to the top of the stack. 
       * <b>Pop</b>: an entity is removed from the top of the stack. 
   * The process of accessing data stored in a serial access memory is similar to manipulating data on a stack.
   * A stack may be defined to have a bounded capacity i.e. if the stack is full and a new entity cannot be added, then it is considered to be in an <b>overflow state</b>. 
   * If the stack is empty and an entity cannot be popped, it is considered to be in an <b>underflow state</b>.
   * <b>Efficiency of stacks</b>: The time is not dependent of the no of items in the stack so it is very efficient. ```O(1)```.</br>
   
   
   
* <b>Queues:</b></br>
   * Queues are an abstract collection that follow FIFO mechanism. The entities in the queue are kept in an order. 
   * Main functionalities include 
       * <b>enqueue</b>: Add an item to the end of the queue. Dequeue: remove an item from the start of the queue. 
       * <b>Front</b>: retrieves the first item from the queue. 
   * A queue may be defined to have a bounded capacity i.e. if the queue is full and a new entity cannot be added, then it is considered to be in an <b>overflow state</b>. 
   * If the queue is empty and an entity cannot be popped, it is considered to be in an <b>underflow state</b>.
   * <b>Efficiency of queues</b>: The time is not dependent of the no of items in the queue so it is very efficient. O(1).
   * <b>A double ended queue (deque)</b>: is an abstract collection which differs from queue in a way that an item can be added/removed from either side of the queue. 
      * An <b>input-restricted deque</b>: is when deletion takes place at either end but insertion takes place at only one end. 
      * An <b>output-restricted deque</b>: is when insertion takes place at either end but deletion takes place only at one end. A common occurrence of deque is doubly linked list.
   * <b>Priority queue</b>: same as queue but has a priority associated with it. Items are retrieved based on their priority</br>
   
   
* <b>Blocking Queues:</b></br>
   * A blocking queue is a queue that blocks when you try to dequeue from it and the queue is empty, or if you try to enqueue items to it and the queue is already full. A thread trying to dequeue from an empty queue is blocked until some other thread inserts an item into the queue. A thread trying to enqueue an item in a full queue is blocked until some other thread makes space in the queue. 
   * [Example on implementing a blocking queue](/src/queue/BlockingQueue.java)</br>
   
   
* <b>Difference between stacks & queues?</b></br>
   * <a href="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/3.png" target="_blank"><img src="https://github.com/anitaa1990/Android-Cheat-sheet/blob/master/media/3.png"></a></br>   
   
</br>

   
* <b>What is a deadlock in Java</b></br>
   * A deadlock occurs when a thread enters a waiting state because a requested system resource is held by another waiting process, which in turn is waiting for another resource held by another waiting process.
   * [Example on how deadlock occurs](/src/deadlock/ThreadLockDemo.java)
   * [Example on how to prevent deadlock](/src/deadlock/ThreadLockFixedDemo.java)</br>
   
   
   
* <b>What is the List interface & Set interface?</b></br>
   * List interface supports for ordered collection of objects and it may contain duplicates. The Set interface provides methods for accessing the elements of a finite mathematical set. Sets do not allow duplicate elements</br>
      

* <b>Difference between ArrayList & Vectors?</b></br>
   * Vectors are thread safe (synchronized) whereas arraylists are not. So performance of arraylists are better than vectors.    * In ArrayList, you have to start searching for a particular element from the beginning of an Arraylist. But in the Vector, you can start searching for a particular element from a particular position in a vector. This makes the search operation in Vector faster than in ArrayList. Vectors have a default size of 10 whereas arraylists size can be dynamic. 
   * <b>Insertion and deletion in ArrayList is slow compared to LinkedList?</b>
       * ArrayList internally uses an array to store the elements, when that array gets filled by inserting elements a new array of roughly 1.5 times the size of the original array is created and all the data of old array is copied to new array.
       * During deletion, all elements present in the array after the deleted elements have to be moved one step back to fill the space created by deletion. In linked list data is stored in nodes that have reference to the previous node and the next node so adding element is simple as creating the node and updating the next pointer on the last node and the previous pointer on the new node. Deletion in linked list is fast because it involves only updating the next pointer in the node before the deleted node and updating the previous pointer in the node after the deleted node.</br>      
      
   
* <b>Implementations of Map?</b></br>
   * <b>TreeMap</b>: sorted based on ascending order of keys. For inserting, deleting, and locating elements in a Map, the HashMap offers the best alternative. If, however, you need to traverse the keys in a sorted order, then TreeMap is your better alternative.
   *	<b>HashTable</b>: Does not allow null values. It is not fail-safe and it is synchronized whereas 
   * <b>HashMap</b> allows null values and it is fail-safe and it is not synchronized. 
   * <b>LinkedHashMap</b>: This is a subclass of Hashmap. The order of insertion is preserved since it has a linkedList.</br>
   
   
* <b>Difference between Enumeration and Iterators?</b></br>
   * <b>Enumeration</b> does not include remove() method whereas iterators do. Enumerators act as read only interface as it provides methods to read and traverse through a collection. 
   * <b>ListIterator</b>: is just like an iterator except it allows access to the collection in either the forward or backward direction</br>
   
   
* <b>How Hashmap works in Java?</b></br>
   * HashMap in Java works on hashing principle. It is a data structure which allows us to store object and retrieve it in constant time O(1) provided we know the key. When we call put method, ```hashcode()``` method of the key object is called so that hash function of the map can find a bucket location to store Entry object.
   * If two different objects have the same hashcode: in this case, a linked list is formed at that bucket location and a new entry is stored as next node. After finding bucket location, we will call ```keys.equals()``` method to identify a correct node in LinkedList and return associated value object for that key in Java HashMap</br>
   
   
   
* <b>Generics in Java</b></br>
   * Before generics, we can store any type of objects in collection i.e. non-generic. Now generics, forces the java programmer to store specific type of objects.
   * Type-safety : We can hold only a single type of objects in generics. It doesn’t allow to store other objects.
   * Type casting is not required: There is no need to typecast the object.
   * Compile-Time Checking: It is checked at compile time so problem will not occur at runtime. The good programming strategy says it is far better to handle the problem at compile time than runtime.
   * Before Generics, we need to type cast.
   ```
   List list = new ArrayList();  
   list.add("hello");  
   String s = (String) list.get(0); //typecasting  
   ```
    * After Generics, we don't need to typecast the object.
    ```
    List<String> list = new ArrayList<String>();  
    list.add("hello");  
    String s = list.get(0);  
    ```
    * A class that can refer to any type is known as generic class. Here, we are using T type 
parameter to create the generic class of specific type. The T type indicates that it can refer to any type (like String, Integer, Employee etc.).The type you specify for the class, will be used to store and retrieve the data.
    * The ? (question mark) symbol represents wildcard element. It means any type. If we write <? extends Number>, it means any child class of Number e.g. Integer, Float, double etc
</br>

#### OOP

* **Explain OOP Concepts.**
    - Object-Oriented Programming is a methodology of designing a program using classes, objects, 
    [inheritance](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)),
    [polymorphism](https://en.wikipedia.org/wiki/Polymorphism_(computer_science)),
    [abstraction](https://en.wikipedia.org/wiki/Abstraction_(software_engineering)), and
    [encapsulation](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)).

* **What is the difference between a constructor and a method?**
    - The name of the constructor is same as that of the class name, whereas the name of the method can be anything.
    - There is no return type of a constructor.
    - When you make an object of a class, then the constructor of that class will be called automatically. 
      But for methods, we need to call it explicitely.
    - Constructors can't be inherited but you can call the constructor of the parent class by calling `super()`.
    - Constructor and a method they both run a block of code but the difference is in calling them.
    - We can call method directly using their name.
    - Constructor Syntax -
        ```java
        public class SomeClassName{
            SomeClassName(parameter_list){ 
                ...
            } 
            ...
        }
        ```
    - Note:
        In the above syntax, the name of the constructor is the same as that of class
        and it has no return type.
        
    - Method Syntax 
        ```java
        public class SomeClassName{
            public void someMethodName(parameter_list){
                ...
            }
            // call method
            someMethodName(parameter_list)
        }
        ```
* **Differences between abstract classes and interfaces?** 
    - An abstract class, is a class that contains both concrete and abstract methods 
    (methods without implementations). An abstract method must be implemented by the abstract class
     sub-classes. Abstract classes cannot be instantiated and need to be extended to be used.
    - An interface is like a blueprint/contract of a class (or it may be thought of as a class with methods, but without their implementation). It contains empty methods that 
    represent, what all of its subclasses should have in common. The subclasses provide the 
    implementation for each of these methods. Interfaces are implemented.

* **What is the difference between iterator and enumeration in java?**
    - In Enumeration we have remove() method and we can only read and traverse through a collection.
    - Iterators can be applied to any collection. In Iterator, we can read and remove items from a collection.

* **Do you agree we use composition over inheritance?** [Learn from here](https://www.journaldev.com/12086/composition-vs-inheritance)

* **Difference between method overloading and overriding.**
        <p align="center">
        <img alt="Overloading and Overriding" src="https://github.com/codeshef/android-interview-questions/blob/master/assets/overloading-vs-overriding.png">
        </p>
    - Overloading happens at compile-time while Overriding happens at runtime: The binding of overloaded method call to its definition happens at compile-time however binding of overridden method call to its definition happens at runtime.
    More info on static vs. dynamic binding: [StackOverflow](https://stackoverflow.com/questions/19017258/static-vs-dynamic-binding-in-java).
    - Static methods can be overloaded which means a class can have more than one static method of same name. Static methods cannot be overridden, even if you declare a same static method in child class it has nothing to do with the same method of parent class as overridden static methods are chosen by the reference class and not by the class of the object.

        So, for example:
        ```java
        public class Animal {
            public static void testClassMethod() {
                System.out.println("The static method in Animal");
            }

            public void testInstanceMethod() {
                System.out.println("The instance method in Animal");
            }
        }

        public class Cat extends Animal {
            public static void testClassMethod() {
                System.out.println("The static method in Cat");
            }

            public void testInstanceMethod() {
                System.out.println("The instance method in Cat");
            }

            public static void main(String[] args) {
                Cat myCat = new Cat();
                myCat.testClassMethod();
                Animal myAnimal = myCat;
                myAnimal.testClassMethod();
                myAnimal.testInstanceMethod();
            }
        }
        ```
        Will output:
        ```java
        The static method in Cat    // testClassMethod() is called from "Cat" reference

        The static method in Animal // testClassMethod() is called from "Animal" reference,
                                    // ignoring actual object inside it (Cat)

        The instance method in Cat  // testInstanceMethod() is called from "Animal" reference,
                                    // but from "Cat" object underneath
        ```

        The most basic difference is that overloading is being done in the same class while for overriding base and child classes are required. Overriding is all about giving a specific implementation to the inherited method of parent class.

        Static binding is being used for overloaded methods and dynamic binding is being used for overridden/overriding methods.
        Performance: Overloading gives better performance compared to overriding. The reason is that the binding of overridden methods is being done at runtime.

        Private and final methods can be overloaded but they cannot be overridden. It means a class can have more than one private/final methods of same name but a child class cannot override the private/final methods of their base class.

        Return type of method does not matter in case of method overloading, it can be same or different. However in case of method overriding the overriding method can have more specific return type (meaning if, for example, base method returns an instance of Number class, all overriding methods can return any class that is extended from Number, but not a class that is higher in the hierarchy, like, for example, Object is in this particular case).

        Argument list should be different while doing method overloading. Argument list should be same in method Overriding.
        It is also a good practice to annotate overridden methods with `@Override` to make the compiler be able to notify you if child is, indeed, overriding parent's class method during compile-time.

* **What are the access modifiers you know? What does each one do?** <br>
   - There are four access modifiers in Java language (from strictest to the most lenient):
        1. `private` *variables*, *methods*, *constructors* or *inner classes* are only visible to its' containing class and its' methods. This modifier is most commonly used, for example, to allow variable access only through getters and setters or to hide underlying implementation of classes that should not be used by user and therefore maintain encapsulation. Singleton constructor is also marked `private` to avoid unwanted instantiation from outside.
        2. `Default` (no keyword is used) this modifier can be applied to *classes*, *variables*, *constructors* and *methods* and allows access from classes and methods inside the same package.
        3. `protected` can be used on *variables*, *methods* and *constructors* therefore allowing access only to subclasses and classes that are inside the same package as protected members' class.
        4. `public` modifier is widely-used on *classes*, *variables*, *constructors* and *methods* to grant access from any class and method anywhere. It should not be used everywhere as it implies that data marked with `public` is not sensitive and can not be used to harm the program.

* **Can an Interface implement another Interface?**
  - Yes, an interface can implement another interface (and more than one), but it needs to use `extends`, rather than `implements` keyword. And while you can not remove methods from parent interface, you can add new ones freely to your sub-interface.

* **What is Polymorphism? What about Inheritance?**
  - Polymorphism in Java has two types: Compile time polymorphism (static binding) and Runtime polymorphism (dynamic binding). Method overloading is an example of static polymorphism, while method overriding is an example of dynamic polymorphism.

    An important example of polymorphism is how a parent class refers to a child class object.  In fact, any object that satisfies more than one IS-A relationship is polymorphic in nature.

    For instance, let’s consider a class `Animal` and let `Cat` be a subclass of `Animal`. So, any cat IS animal. Here, Cat satisfies the IS-A relationship for its own type as well as its super class Animal.
  - Inheritance can be defined as the process where one class acquires the properties (methods and fields) of another. With the use of inheritance the information is made manageable in a hierarchical order.

    The class which inherits the properties of other is known as subclass (derived class, child class) and the class whose properties are inherited is known as superclass (base class, parent class).

    Inheritance uses the keyword `extends` to inherit the properties of a class. Following is the syntax of extends keyword.
    ```java
    class Super {
       .....
       .....
    }
    class Sub extends Super {
       .....
       .....
    }
    ```

* **Multiple inheritance in Classes and Interfaces in java** [Learn from here](http://codeinventions.blogspot.in/2014/07/can-interface-extend-multiple.html)

* **What are the design patterns?** [Learn from here](https://blog.mindorks.com/mastering-design-patterns-in-android-with-kotlin)
    - Creational patterns
        - Builder [Wikipedia](https://en.wikipedia.org/wiki/Builder_pattern?oldformat=true)
        - Factory [Wikipedia](https://en.wikipedia.org/wiki/Factory_method_pattern?oldformat=true)
        - Singleton [Wikipedia](https://en.wikipedia.org/wiki/Singleton_pattern)
        - Monostate [Wikipedia](http://wiki.c2.com/?MonostatePattern)
        - Fluent Interface Pattern [Wikipedia](https://martinfowler.com/bliki/FluentInterface.html)
    - Structural patterns
        - Adapter [Wikipedia](https://en.wikipedia.org/wiki/Adapter_pattern?oldformat=true)
        - Decorator [Wikipedia](https://en.wikipedia.org/wiki/Decorator_pattern?oldformat=true)
        - Facade [Wikipedia](https://en.wikipedia.org/wiki/Facade_pattern?oldformat=true)
    - Behavioural patterns
        - Chain of responsibility [Wikipedia](https://en.wikipedia.org/wiki/Chain-of-responsibility_pattern?oldformat=true)
        - Iterator [Wikipedia](https://en.wikipedia.org/wiki/Iterator_pattern?oldformat=true)
        - Strategy [Wikipedia](https://en.wikipedia.org/wiki/Strategy_pattern?oldformat=true)

#### Collections and Generics

* **Arrays Vs ArrayLists** - [Learn from here](https://stackoverflow.com/questions/32020000/what-is-the-difference-between-an-array-arraylist-and-a-list/32020072) and [here](https://www.youtube.com/watch?v=SMtSW3Zke_k)

* **HashSet Vs TreeSet** - [Learn from here](https://stackoverflow.com/questions/25602382/java-hashset-vs-treeset-when-should-i-use-over-other)

* **HashMap Vs Set** - [Learn from here](https://stackoverflow.com/questions/2773824/difference-between-hashset-and-hashmap)

* **Stack Vs Queue** - [Learn from here](https://afteracademy.com/tech-interview/ds-algo-concepts/stack-and-queue)

* **Explain Generics in Java?**
    - Generics were included in Java language to provide stronger type checks, by allowing the programmer to define, which classes can be used with other classes
        > In a nutshell, generics enable types (classes and interfaces) to be parameters when defining classes, interfaces and methods. Much like the more familiar formal parameters used in method declarations, type parameters provide a way for you to re-use the same code with different inputs. The difference is that the inputs to formal parameters are values, while the inputs to type parameters are types. ([Official Java Documentation](https://docs.oracle.com/javase/tutorial/java/generics/why.html))

    - This means that, for example, you can define:
        ```java
        List<Integer> list = new ArrayList<>();
        ```
        And let the compiler take care of noticing, if you put some object, of type other than `Integer` into this list and warn you.
    - It should be noted that standard class hierarchy *does not* apply to generic types. It means that `Integer` in `List<Integer>` is not inherited from `<Number>` - it is actually inherited directly from `<Object>`. You can still put some constraints on what classes can be passed as a parameter into a generic by using [wildcards](https://docs.oracle.com/javase/tutorial/extra/generics/wildcards.html) like `<?>`, `<? extends MyCustomClass>` or `<? super Number>`.
    - While generics are very useful, late inclusion into Java language has put some restraints on their implementation - backward compatibility required them to remain just "syntactic sugar" - they are erased ([type erasure](https://docs.oracle.com/javase/tutorial/java/generics/erasure.html)) during compile-time and replaced with `object` class.

* **What is Java PriorityQueue?**
        - In Priority Queue, each element is having some priority and all the elements are present in a queue. The operations are performed based on the priority.

#### Objects and Primitives

* **How is `String` class implemented? Why was it made immutable?**
  - There is no primitive variant of `String` class in Java language - all strings are just wrappers around underlying array of characters, which is declared `final`. This means that, once a `String` object is instantiated, it cannot be changed through normal tools of the language (Reflection still can mess things up horribly, because in Java no object is truly immutable). This is why `String` variables in classes are the first candidates to be used, when you want to override `hashCode()` and `equals()` of your class - you can be sure, that all their required contracts will be satisfied.
    > Note: The String class is immutable, so that once it is created a String object cannot be changed. The String class  has a number of methods, some of which will be discussed below, that appear to modify strings. Since strings are  immutable, what these methods really do is create and return a new string that contains the result of the operation. ([Official Java Documentation](https://docs.oracle.com/javase/tutorial/java/data/strings.html))

    This class is also unique in a sense, that, when you create an instance like this:
    ```java
    String helloWorld = "Hello, World!";
    ```
    `"Hello, World!"` is called a *literal* and compiler creates a `String` object with its' value. So
    ```java
    String capital = "Hello, World!".toUpperCase();
    ```
    is a valid statement, that, firstly, will create an object with literal value "Hello, World!" and then will create and return another object with value "HELLO, WORLD!"
  - `String` was made immutable to prevent malicious manipulation of data, when, for example, user login or other sensitive data is being send to a server.

* **What does it means to say that a `String` is immutable?**
    - It means that once created, `String` object's `char[]` (its' containing value) is declared `final` and, therefore, it can not be changed during runtime.

* **What is `String.intern()`? When and why should it be used?**
    - `String.intern()` is used to mange memory in Java code. It is used when we have duplicates value in different strings. When you call the `String.intern()`, then if in the String pool that string is present then the `equals()` method will return true and it will return that string only.

* **Can you list 8 primitive types in java?**
    - `byte`
    - `short`
    - `int`
    - `long`
    - `float`
    - `double`
    - `char`
    - `String`
    - `boolean`

* **What is the difference between an Integer and int?**
  - `int` is a primitive data type (with `boolean`, `byte`, `char`, `short`, `long`, `float` and `double`), while `Integer` (with `Boolean`, `Byte`, `Character`, `Short`,`Long`, `Float` and `Double`) is a [wrapper](https://docs.oracle.com/javase/tutorial/java/data/numberclasses.html) class that encapsulates primitive data type, while providing useful methods to perform different tasks with it.

* **What is Autoboxing and Unboxing?**
  - Autoboxing and Unboxing is the process of automatic wrapping (putting in a box) and unwrapping (getting the value out) of primitive data types, that have "wrapper" classes. So `int` and `Integer` can (almost always) be used interchangeably in Java language, meaning a method `void giveMeInt(int i) { ... }` can take `int` as well as `Integer` as a parameter.

* **Typecast in Java**
    - In Java, you can use casts to polymorph one class into another, compatible one. For example:
        ```java
            long i = 10l;
            int j = (int) i;
            long k = j;
        ```
        Here we see, that, while narrowing (`long i` -> `int j`) requires an explicit cast to make sure the programmer realizes, that there may be some data or precision loss, widening (`int j` -> `long k`) does not require an explicit cast, because there can be no data loss (`long` can take larger numbers than `int` allows).

* **Do objects get passed by reference or value in Java? Elaborate on that.**
    - In Java all primitives and objects are passed by value, meaning that their copy will be manipulated in the receiving method. But there is a caveat - when you pass an object reference into a method, a *copy of this reference* is made, so it still points to the same object. This means, that any changes that you make to the insides of this object are retained, when the method exits.
        ```java
        public class Pointer {

            int innerField;

            public Pointer(int a) {
                this.innerField = a;
            }
        }
        ```
        ```java
        public class ValueAndReference {

            public static void main(String[] args) {

                Pointer a = new Pointer(0);
                int b = 1;

                print("Before:");
                print("b = " + b);
                print("a.innerField = " + a.innerField);
                exampleMethod(a, b);
                print("After:");
                print("b = " + b);
                print("a.innerField = " + a.innerField);
            }

            static void exampleMethod(Pointer a, int b) {
                a.innerField = 2;
                b = 10;
            }

            static void print(String text) {
                System.out.println(text);
            }
        }
        ```
        Will output:
        ```java
            Before:

            b = 1

            a.innerField = 0

            After:

            b = 1        // a new local int variable was created and operated on, so "b" didn't change

            a.innerField = 2 // Pointer a got its' innerField variable changed
                             //  from 0 to 2, because method was operating on
                             //  the same reference to an instance
        ```

* **What is the difference between instantiation and initialization of an object?** - [Learn from here](https://docs.oracle.com/javase/tutorial/java/javaOO/objectcreation.html)

* **What the difference between local, instance and class variables?**
  - Local variables exist only in methods that created them, they are stored separately in their respected Thread Stack (for more information, see question about Java Memory Model) and cannot have their reference passed outside of the method scope. That also means that they cannot be assigned any access modifier or made `static` - because they only exist during enclosing method's execution and those modifiers just do not make sense, since no other outside method can get them anyway.
  - Instance variables are the ones, that are declared in classes and their value can be different from one instance of the class to another, but they always require that class' instance to exist.
  - Class variables are those, that are marked with `static` keyword in their class' body. They can only have one value across all instances of that class (changing it in one place will change it in their class and, therefore, in all instances) and can even be retrieved without that class' instance (if their access modifier allows it).

#### Java Memory Model and Garbage Collector

* **What is garbage collector? How does it work?**
  - All objects are allocated on the heap area managed by the JVM.
  As long as an object is being referenced, the JVM considers it alive.
  Once an object is no longer referenced and therefore is not reachable by the application code,
  the garbage collector removes it and reclaims the unused memory.

* **What is Java Memory Model? What contracts does it guarantee? How are its' Heap and Stack organized?** - [Learn from here](http://tutorials.jenkov.com/java-concurrency/java-memory-model.html)

* **What is memory leak and how does Java handle it?** - [Learn from here](https://developers.redhat.com/blog/2014/08/14/find-fix-memory-leaks-java-application/)

* **What are strong, soft, weak and phantom references in Java?** - [Learn from here](https://dzone.com/articles/weak-soft-and-phantom-references-in-java-and-why-they-matter)

#### Concurrency

* **What does the keyword `synchronized` mean?** [Learn from here](https://stackoverflow.com/a/1085745/2621950)

* **What is a `ThreadPoolExecutor`?** [Learn from here](https://blog.mindorks.com/threadpoolexecutor-in-android-8e9d22330ee3)

* **What is `volatile` modifier?** [Learn from here](http://tutorials.jenkov.com/java-concurrency/volatile.html)

* **The classes in the atomic package expose a common set of methods: `get`, `set,`, `lazyset`, `compareAndSet`, and `weakCompareAndSet`. Please describe them.**

#### Exceptions

* **How does the `try{}`, `catch{}`, `finally` works?** - [Learn from here](https://www.youtube.com/watch?v=Z_5e8MjRWnc&list=PL6nth5sRD25g_M_OgsMQgYIrESzzkGLME&index=13)

* **What is the difference between a `Checked Exception` and an `Un-Checked Exception`?** - [Learn from here](https://www.w3schools.in/java-questions-answers/difference-between-checked-and-unchecked-exceptions-in-java/)

#### Others

* **What is serialization? How do you implement it?**
    - Serialization is the process of converting an object into a stream of bytes in order to store
    an object into memory, so that it can be recreated at a later time, while still keeping the
    object's original state and data. In Android you may use either the Serializable, Externalizable (implements Serializable) or Parcelable interfaces.
    - While Serializable is the easiest to implement, Externalizable may be used if you need to insert custom logic into the process of serialization (although it is almost never used nowadays as it is considered a relic from early versions of Java). But it is highly recommended to use Parcelable in Android instead, as Parcelable was created exclusively for Android and it performs about 10x faster than Serializable, because Serializable uses reflection, which is a slow process and tends to create a lot of temporary objects and it may cause garbage collection to occur more often.
    - To use Serializable all you have to do is implement the interface:

        ```java
        /**
        *  Implementing the Serializable interface is all that is required
        */
        public class User implements Serializable {

            private String name;
            private String email;

                public User() {
                }

                public String getName() {
                    return name;
                }

                public void setName(final String name) {
                    this.name = name;
                }

                public String getEmail() {
                    return email;
                }

                public void setEmail(final String email) {
                    this.email = email;
                }
            }
        ```
    - Parcelable requires a bit more work:
        ```java
            public class User implements Parcelable {

                private String name;
                private String email;

                /**
                 * Interface that must be implemented and provided as a public CREATOR field
                 * that generates instances of your Parcelable class from a Parcel.
                 */
                public static final Creator<User> CREATOR = new Creator<User>() {

                    /**
                     * Creates a new USer object from the Parcel. This is the reason why
                     * the constructor that takes a Parcel is needed.
                     */
                    @Override
                    public User createFromParcel(Parcel in) {
                        return new User(in);
                    }

                    /**
                     * Create a new array of the Parcelable class.
                     * @return an array of the Parcelable class,
                     * with every entry initialized to null.
                     */
                    @Override
                    public User[] newArray(int size) {
                        return new User[size];
                    }
                };

                public User() {
                }

                /**
                 * Parcel overloaded constructor required for
                 * Parcelable implementation used in the CREATOR
                 */
                private User(Parcel in) {
                    name = in.readString();
                    email = in.readString();
                }

                public String getName() {
                    return name;
                }

                public void setName(final String name) {
                    this.name = name;
                }

                public String getEmail() {
                    return email;
                }

                public void setEmail(final String email) {
                    this.email = email;
                }

                @Override
                public int describeContents() {
                    return 0;
                }

                /**
                 * This is where the parcel is performed.
                 */
                @Override
                public void writeToParcel(final Parcel parcel, final int i) {
                    parcel.writeString(name);
                    parcel.writeString(email);
                }
            }
        ```
        Note: For a full explanation of the <b>describeContents()</b> method see [StackOverflow](https://stackoverflow.com/questions/4076946/parcelable-where-when-is-describecontents-used/4914799#4914799).
        In Android Studio, you can have all of the parcelable code auto generated for you, but like with everything else, it is always a good thing to try and understand everything that is happening.

* **What is `transient` modifier?** [Learn from here](https://www.javatpoint.com/transient-keyword)

* **What are anonymous classes?** [Learn from here](https://docs.oracle.com/javase/tutorial/java/javaOO/anonymousclasses.html)

* **What is the difference between using `==` and `.equals` on an object?** - [Learn from here](https://www.youtube.com/watch?v=aVjnX1MIHB8)

* **What is the `hashCode()` and `equals()` used for?** - [Learn from here](https://www.geeksforgeeks.org/equals-hashcode-methods-java/)

* **Why would you not call abstract method in constructor?** - [Learn from here](https://stackoverflow.com/questions/15327417/is-it-ok-to-call-abstract-method-from-constructor-in-java)

* **When would you make an object value `final`?**

* **What are these `final`, `finally` and `finalize` keywords?**
  - `final` is a keyword in the java language. It is used to apply restrictions on class, method and variable. Final class can't be inherited, final method can't be overridden and final variable value can't be changed.
    ```java
    class FinalExample {
        public static void main(String[] args) {
            final int x=100;
            x=200;//Compile Time Error because x is final
        }
    }
    ```
  - `finally` is a code block and is used to place important code, it will be executed whether exception is handled or not.
    ```java
    class FinallyExample {
        public static void main(String[] args) {
            try {
                int x=300;
            }catch(Exception e) {
                System.out.println(e.getMessage());            }
            finally {
                System.out.println("finally block is executed");
            }
        }
    }
    ```
  - `Finalize` is a method used to perform clean up processing just before object is garbage collected.
    ```java
    class FinalizeExample {
        public void finalize() {
            System.out.println("finalize called");
        }

        public static void main(String[] args) {
            FinalizeExample f1=new FinalizeExample();
            FinalizeExample f2=new FinalizeExample();
            f1=null;
            f2=null;
            System.gc();
        }
    }
    ```

* **What is the difference between "throw" and "throws" keyword in Java?**
    - `throws` is just used to indicated which exception is to be thrown. But the `throw` keyword is used to throw some exception from any static block or any method.

* **What does the `static` word mean in Java?**
    - In case of `static` variable it means that this variable (its' value or the object it references) spans across all instances of enclosing class (changing it in one instance affects all others), while in case of `static` methods it means that these methods can be invoked without an instance of their enclosing class. It is useful, for example, when you create util classes that need not be instantiated every time you want to use them.

* **Can a `static` method be overridden in Java?**
    - While child class can override a static method with another static method with the same signature (return type can be down-casted), it is not truly overridden - it becomes "hidden", but both methods can still be accessed under right circumstances (see question about overloading/overriding above).

* **When is a `static` block run?**
    - Code inside static block is executed only once: the first time you make an object of that class or the first time you access a static member of that class (even if you never make an object of that class).

* **What is reflection?**
    - You can inspect classes, interfaces, fields, and method at runtime with the help of reflection and the best part is that you need not know the names of these classes, methods, etc.

* **What is Dependency Injection?** [Learn from here](https://www.youtube.com/watch?v=Grzqz-B3NWU)

* **How is a `StringBuilder` implemented to avoid the immutable string allocation problem?** - [Learn from here](https://stackoverflow.com/questions/54023816/how-is-a-stringbuilder-implemented-to-avoid-the-immutable-string-allocation-prob)

* **Difference between `StringBuffer` and `StringBuilder`?** - [Learn from here](https://www.journaldev.com/538/string-vs-stringbuffer-vs-stringbuilder)

* **What is the difference between fail-fast and fail-safe iterators in Java?**
    - Fail-safe iterator will not throw any exception even if the collection is modified while iteration over it. But in Fail-safe iterator, it throws a ConcurrentModificationException when you try to modify the collection while using it.

* **What is Java NIO?** - [Learn from here](https://en.wikipedia.org/wiki/Non-blocking_I/O_(Java))

* **Monitor and Synchronization** - [Learn from here](https://www.youtube.com/watch?v=oLTw1aJpSho)

* **Tell some advantages of Kotlin.** - [Learn from here](https://www.youtube.com/watch?v=kRhivT-jKzY&t=16s)

* **What is the difference between `val` and `var`?** - [Learn from here](https://stackoverflow.com/questions/44200075/val-and-var-in-kotlin)

* **What is the difference between `const` and `val`?** - [Learn from here](https://blog.mindorks.com/what-is-the-difference-between-const-and-val)

* **How to ensure `null` safety in Kotlin?** - [Learn from here](https://blog.mindorks.com/safecalls-vs-nullchecks-in-kotlin)

* **When to use `lateint` keyword used in Kotlin?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-lateinit-vs-lazy)

* **How to check if a `lateinit` variable has been initialized?** - [Learn from here](https://blog.mindorks.com/how-to-check-if-a-lateinit-variable-has-been-initialized)

* **How to do lazy initialization of variables in Kotlin?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-lateinit-vs-lazy) and [here](https://www.youtube.com/watch?v=yEX9_PeNRy4)

* **What are `companion objects` in Kotlin?** - [Learn from here](https://blog.mindorks.com/companion-object-in-kotlin)

* **What are the visibility modifiers in Kotlin?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-visibility-modifiers-private-protected-internal-public)

* **What is the equivalent of Java static methods in Kotlin?** - [Learn from here](https://blog.mindorks.com/what-is-the-equivalent-of-java-static-methods-in-kotlin)

* **What is a data class in Kotlin?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-data-class)

* **How to create a Singleton class in Kotlin?** - [Learn from here](https://blog.mindorks.com/how-to-create-a-singleton-class-in-kotlin)

* **What is the difference between `open` and `public` in Kotlin?** - [Learn from here](https://blog.mindorks.com/understanding-open-keyword-in-kotlin)

* **Explain the use-case of `let`, `run`, `with`, `also`, `apply` in Kotlin.** - [Learn from here](https://blog.mindorks.com/using-scoped-functions-in-kotlin-let-run-with-also-apply) and [here](https://www.youtube.com/watch?v=AiFBEH54Xpw)

* **Difference between List and Array types in Kotlin** - [Learn from here](https://blog.mindorks.com/difference-between-list-and-array-types-in-kotlin)

* **What are `Labels` in Kotlin?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-returns-jumps-labels)

* **What is an `Init` block in Kotlin?** - [Learn from here](https://blog.mindorks.com/understanding-init-block-in-kotlin)

* **Explain `pair` and `triple` in Kotlin.** - [Learn from here](https://blog.mindorks.com/pair-and-triple-in-kotlin)

* **How to choose between `apply` and `with`?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-apply-vs-with)

* **How to choose between `switch` with `when`?** - [Learn from here](https://blog.mindorks.com/replace-switch-with-when-in-kotlin)

* **What are Coroutines in Kotlin?** - [Learn from here](https://blog.mindorks.com/mastering-kotlin-coroutines-in-android-step-by-step-guide)

* **What is Coroutine Scope?** - [Learn from here](https://blog.mindorks.com/mastering-kotlin-coroutines-in-android-step-by-step-guide)

* **What is Coroutine Context?** - [Learn from here](https://blog.mindorks.com/mastering-kotlin-coroutines-in-android-step-by-step-guide)

* **Launch vs Async in Kotlin Coroutines** - [Learn from here](https://www.youtube.com/watch?v=nC30UiDv8Xc)

* **What is inline function in Kotlin?** - [Learn from here](https://blog.mindorks.com/understanding-inline-noinline-and-crossinline-in-kotlin)

* **When to use Kotlin sealed classes?** - [Learn from here](https://blog.mindorks.com/learn-kotlin-sealed-classes)

* **Explain function literals with receiver in Kotlin?** - [Learn from here](https://blog.mindorks.com/function-literals-with-receiver-in-kotlin)

* **Tell about Kotlin DSL.** - [Learn from here](https://blog.mindorks.com/mastering-kotlin-dsl-in-android-step-by-step-guide)

* **What are higher-order functions in Kotlin?** - [Learn from here](https://blog.mindorks.com/understanding-higher-order-functions-and-lambdas-in-kotlin)

* **What are Lambdas in Kotlin** - [Learn from here](https://blog.mindorks.com/understanding-higher-order-functions-and-lambdas-in-kotlin)

* **Tell about the Collections in Kotlin** - [Learn from here](https://www.youtube.com/watch?v=XeRt2ZZ-jkA)


### Other Topics

* **Describe how REST APIs work. What is REST?** - [Learn from here](https://www.youtube.com/watch?v=1wSEI6_SzMU) and [here](https://www.youtube.com/watch?v=HgXAoBomGcA)

* **Describe SQLite.** - [Learn from here](https://blog.mindorks.com/android-sqlite-database-in-kotlin) and [here](https://www.youtube.com/watch?v=9OHzXUo3Ymk)

* **Describe database.** - [Learn from here](https://afteracademy.com/blog/what-is-a-database-and-dbms)

* **How do you control the application version update to specific number of users?**

* **Can we identify users who have uninstalled our application?**

* **Android Development Best Practices.** - [Learn from here](https://blog.mindorks.com/android-development-best-practices-83c94b027fd3)

* **Android Code Style And Guidelines.** - [Learn from here](https://blog.mindorks.com/android-code-style-and-guidelines-d5f80453d5c7)

* **Have you tried Kotlin?** - [Learn from here](https://blog.mindorks.com/why-you-must-try-kotlin-for-android-development-e14d00c8084b)

* **What are the metrics that you should measure continuously while android application development?** - [Learn from here](https://blog.mindorks.com/android-app-performance-metrics-a1176334186e)

* **What is Chrome Custom Tabs? How to display web content in your app?** - [Learn from here](https://blog.mindorks.com/android-browser-lets-launch-chrome-custom-tabs-with-kotlin)

* **How to avoid API keys from check-in into VCS?** - [Learn from here](https://blog.mindorks.com/using-local-properties-file-to-avoid-api-keys-check-in-into-version-control-system)

* **How does the Kotlin Multiplatform work?** - [Learn from here](https://blog.mindorks.com/how-does-the-kotlin-multiplatform-work)

* **How to use Memory Heap Dumps data?** - [Learn from here](https://blog.mindorks.com/how-to-use-memory-heap-dumps-data)

* **How to implement Dark Theme in your app?** - [Learn from here](https://blog.mindorks.com/build-material-and-dark-themes-apps-using-style-in-android)

* **Have you tried Jetpack compose?** - [Learn from here](https://blog.mindorks.com/using-jetpack-compose-to-build-ui-in-android)

* **How to secure the API keys used in an app?** - [Learn from here](https://blog.mindorks.com/securing-api-keys-using-android-ndk)

* **How to convert check Java equivalent code of Kotlin?** - [Learn from here](https://blog.mindorks.com/how-to-convert-a-kotlin-source-file-to-a-java-source-file)

* **Tell something about memory usage in Android.** - [Learn from here](https://blog.mindorks.com/understanding-memory-usage-in-android)

* **What is Benchmarking?** - [Learn from here](https://blog.mindorks.com/improving-android-app-performance-with-benchmarking)

* **Can you create transparent activity in Android?** - [Learn from here](https://blog.mindorks.com/how-to-create-a-transparent-activity-in-android)

* **How to use Android Sensors?** - [Learn from here](https://blog.mindorks.com/using-android-sensors-android-tutorial)

* **Explain Annotation processing.**  - [Learn from here](https://blog.mindorks.com/android-annotation-processing-tutorial-part-1-a-practical-approach)

* **How to increase the Notification delivery rate?** [Learn from here](https://blog.mindorks.com/how-to-increase-push-notification-delivery-rate-in-android)

* **How does the notification system work?** [Learn from here](https://blog.mindorks.com/how-to-increase-push-notification-delivery-rate-in-android)

* **How to show local Notification at an exact time?** [Learn from here](https://blog.mindorks.com/how-to-increase-push-notification-delivery-rate-in-android)
