# Java and Swift Language Comparison
## Nicole Dillon

### Language purpose/genesis
#### Swift
Apple began developing Swift in 2010 to serve as a safer, faster, and more concise replacement to Objective-C. Swift is used to create apps for Apple products. It was designed to give developers more freedom, to create code that is easier to read and maintain, and to save time by requiring less code to express more complex ideas. It introduced a system to help combat common programming errors, like null pointers.

#### Java
Java was released by Sun Microsystems in 1995 as a responce to C and C++ and was designed to follow five primary goals:
1. simple, object-oriented, and familiar
2. robust and secure
3. architecture-neutral and portable
4. execute with high prerformance
5. interpreted, threaded, and dynamic

### Unique features of the language
#### Swift
Swift introduces optional types. Optionals handle the absense of value and state that there either is a value and what is is equal to, or there is no value at all.
```swift
//optional int that does not have a value
var optionalInt: Int? = nil
```
#### Java
Java runs on the Java Virtual Machine, thus making the Java code platform independent.

### Namespaces
#### Swift
Namespaces are implicit and not needed due to Swift Modules, as all class are explicitly scoped by the module. 

#### Java
In Java, namespaces are called packages and are implemented using the keyword `package`. A package contains a group of related classes and interfaces. The keyword `import` is used to access a class outside of a package.
```java
import java.util.Vector;
```

### Types
#### Swift
Swift has many built-in data types like Int, Float, Double, Bool, String, Character, or Optional, but also allows the developer to create their own value types by using type aliases. Similar to Java, types can be passed either by reference or by value. Swift also has a type interface, which can infer what type a variable is without having to be explicitly stated.
```swift
//declare int
var heartRate: Int = 85

//type interface
var heartRate = 85

//optional
var heartRate: Int? = nil

//type aliases
typealias HeartRate = Int
var vitals: HeartRate = 85

```
#### Java
Java supports eight primitive data types, reference types, and also has the ability to create new object types. These can either be passed by value or reference.
```java
//primitive data type
boolean bool = true;
byte b = 126;
char c = 'a';
short s = 32700;
int i = 1;
double d = 2.0;

//reference type
String str = "Hello world"
```

### Classes
#### Swift

Classes can be initialized using the keyword `init` and deinitialized using the keyword `deinit`. Although Swift usually automatically deallocates instances and frees up any resource it has assigned, deinitializing a class may be required in some instances. For example, if you create a class that opens a file, you may need to close that file.

```swift
//defining class
class ExampleClass {
	var exampleBoolean: Boolean
	var exampleDouble: Double
	//initializing class
	init() {
		exampleBoolean = true
		exampleDouble = 0.0
	}
	//deinitializing
	deinit{
		//perform deinitialization here
	}
}

//defining class with default intializers
class DefaultInitClass {
	var exampleBoolean = true
	var exampleDouble = 0.0
}

//creating instance of class
let instanceOfClass = ExampleClass()

```

#### Java

Classes are defined using a constructor with the same name as the class. To create an instance of a class, use the keyword `new` and then call the constructor. There is no destructing since Java has a garbage collector.

```java
//defining class
public class ExampleClass {
	public int x;
}

//create instance of class
ExampleClass ec = new ExampleClass();
```

	
### Instance reference name in data type (class)
#### Swift
The `self` keyword is used to reference an instance in Swift.
```swift
class Example {
    let x: Double
    init(x: Double) {
        self.x   = x
    }
}
```
#### Java
The `this` keyword is used to reference the current object in an instance of a class in Java and resolves conflicts between method parameters and instance fields/methods of the invoked class.
```java
public class ClassName {
	public int x;

	public ClassName(int x) {
		this.x = x;
	}
}
```
	
### Properties
#### Swift
Properties associate values with a particular class, structure, or enumeration. Stored properties store constant and variable values as part of an instance, whereas computed properties calculate (rather than store) a value. Computed properties are provided by classes, structures, and enumerations. Stored properties are provided only by classes and structures. 

```swift
//stored property
struct FixedLengthRange {
    var firstValue: Int
    let length: Int
}
var rangeOfThreeItems = FixedLengthRange(firstValue: 0, length: 3)
// the range represents integer values 0, 1, and 2
rangeOfThreeItems.firstValue = 6
// the range now represents integer values 6, 7, and 8

//computed property
struct Point {
    var x = 0.0, y = 0.0
}
struct Size {
    var width = 0.0, height = 0.0
}
struct Rect {
    var origin = Point()
    var size = Size()
    var center: Point {
        get {
            let centerX = origin.x + (size.width / 2)
            let centerY = origin.y + (size.height / 2)
            return Point(x: centerX, y: centerY)
        }
        set(newCenter) {
            origin.x = newCenter.x - (size.width / 2)
            origin.y = newCenter.y - (size.height / 2)
        }
    }
}
var square = Rect(origin: Point(x: 0.0, y: 0.0),
                  size: Size(width: 10.0, height: 10.0))
let initialSquareCenter = square.center
square.center = Point(x: 15.0, y: 15.0)
print("square.origin is now at (\(square.origin.x), \(square.origin.y))")
// Prints "square.origin is now at (10.0, 10.0)"

```

[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Properties.html#//apple_ref/doc/uid/TP40014097-CH14-ID254)


#### Java
Getters and setters must be written by the developer. Java does not have backing variables or computed properties.

```java
private int x;

public void setX(int x) {
	this.x = x;
}
public void getX() {
	return x;
}
```
### Interfaces / protocols
#### Swift
A protocol defines a blueprint of methods, properties, and other requirements that suit a particular task or piece of functionality. The protocol can then be adopted by a class, structure, or enumeration to provide an actual implementation of those requirements. Any type that satisfies the requirements of a protocol is said to conform to that protocol.

```swift
protocol SomeProtocol {
    // protocol definition goes here
}
```
[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Protocols.html#//apple_ref/doc/uid/TP40014097-CH25-ID267)

#### Java
Java supports interfaces and are defined by using the keyword `interface`. An interface is a reference type that acts similar to a class. Classes can implement multiple interfaces and can be used for abstraction. When implemented by a class, all interface methods must be declared as public. Java also supports marker interfaces, or an empty interface.

```java
public class Cricket implements Insect {
	//all Insect methods and Cricket methods
}
```

### Inheritance / extension
#### Swift
Extensions add new functionality to an existing class, structure, enumeration, or protocol type. This includes the ability to extend types for which you do not have access to the original source code (known as retroactive modeling). You can even extend a protocol to provide implementations of its requirements or add additional functionality that conforming types can take advantage of.
```swift
extension SomeType: SomeProtocol, AnotherProtocol {
    // implementation of protocol requirements goes here
}
```
[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Extensions.html#//apple_ref/doc/uid/TP40014097-CH24-ID151)

#### Java
Inheritance allows the developer to derive new classes from existing classes. Java uses the keyword `extends` followed by a class name to specify what class it would like to inherit from.Java does not support multiple inheritance
```java
class Dog extends Pet {
	//all pet fields/methods as well as new dog fields/methods
}
```

### Reflection
#### Swift
Refelection in swift is done using the struct mirror. A mirror describes the parts that make up a particular instance, such as the instance’s stored properties, collection or tuple elements, or its active enumeration case. Mirrors also provide a “display style” property that suggests how this mirror might be rendered. Playgrounds and the debugger use the Mirror type to display representations of values of any type.

```swift
struct Point {
    let x: Int, y: Int
}

let p = Point(x: 21, y: 30)
print(String(reflecting: p))
// Prints "▿ Point
//           - x: 21
//           - y: 30"
```
[Swift Documentation](https://developer.apple.com/documentation/swift/mirror)

#### Java
Java supports reflection. Reflection allows inspection of classes, interfaces, fields and methods at runtime without knowing the names of the interfaces, fields, methods at compile time. It is also possible to instantiate new objects, invoke methods and get/set field values using reflection.

```java
Method[] methods = MyObject.class.getMethods();

for(Method method : methods){
    System.out.println("method = " + method.getName());
}
```

[Java Reflection](http://tutorials.jenkov.com/java-reflection/index.html)

### Memory management
#### Swift
Swift does not have garbage collection so it uses Automatic Reference Counting (ARC) to track and manage your app’s memory usage. In most cases, this means that memory management “just works” in Swift, and you do not need to think about memory management yourself. ARC automatically frees up the memory used by class instances when those instances are no longer needed.

[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/AutomaticReferenceCounting.html#//apple_ref/doc/uid/TP40014097-CH20-ID48)

#### Java
Java has garbage collection, which tracks all the objects and frees the memory if the program no longer references that object.
	
### Comparisons of references and values
#### Swift
 `===` tests whether two object references both refer to the same object instance. `==` compares values with the same value type.

```swift
1 == 1 //true

let x = SomeClass()
let y = x
x === y //true
```

#### Java
`.equals()` compares values inside of object while `==` checks to see if two variables reference the same object.

```java
String x = "hello world";
String y = "hello world";
String z = y;
x == y; //false
z == y; //true
x.equals(y); //true
```

### Null/nil references
#### Swift
`nil` is used to represent a valueless state. Optionals are the only variables that are able to be assigned a nil. In order to access the value of a nil optional, `!` must be placed after the optional name to unwrap it.

```swift
//declare optional nil
var i: Int? = nil

//unwrap optional
x!
```

#### Java
Java uses `null` and it can be assigned to any reference type. If `null` is used incorrectly, a `NullPointerException` is thrown.
```java
Integer i = null;
```
	
### Errors and exception handling
#### Swift
There are four ways to handle errors in Swift. You can propagate the error from a function to the code that calls that function, handle the error using a do-catch statement, handle the error as an optional value, or assert that the error will not occur.

```swift
//propagating error
func canThrowErrors() throws -> String


//do-catch
do {
    try expression
    statements
} catch pattern 1 {
    statements
} catch pattern 2 where condition {
    statements
} catch {
    statements
}

//converting to optional value
func fetchData() -> Data? {
    if let data = try? fetchDataFromDisk() { return data }
    if let data = try? fetchDataFromServer() { return data }
    return nil
}

//assert that the error will not occur
let photo = try! loadImage(atPath: "./Resources/John Appleseed.jpg")

```

[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/ErrorHandling.html#//apple_ref/doc/uid/TP40014097-CH42-ID508)

#### Java
A method catches an exception using a combination of the `try` and `catch` keywords. A try/catch block is placed around the code that might generate an exception. The finally block follows a try block or a catch block. A finally block of code always executes, irrespective of occurrence of an Exception. Using a finally block allows you to run any cleanup-type statements that you want to execute, no matter what happens in the protected code. If a method does not handle a checked exception, the method must declare it using the throws keyword. The throws keyword appears at the end of a method's signature. You can throw an exception, either a newly instantiated one or an exception that you just caught, by using the throw keyword.

```java
//try catch block
try {
   // Protected code
} catch (ExceptionType1 e1) {
   // Catch block
} catch (ExceptionType2 e2) {
   // Catch block
} catch (ExceptionType3 e3) {
   // Catch block
} finally {
   // The finally block always executes.
}

//throws
import java.io.*;
public class className {

   public void deposit(double amount) throws RemoteException {
      // Method implementation
      throw new RemoteException();
   }
   // Remainder of class definition
}
```
[tutorialspoint](https://www.tutorialspoint.com/java/java_exceptions.htm)

### Lambda expressions, closures, or functions as types
#### Swift
Closures are self-contained blocks of functionality that can be passed around and used in your code

```swift
//closure expression syntax
{ (parameters) -> return type in
    statements
}

//closure as reference type
let alsoIncrementByTen = incrementByTen
alsoIncrementByTen()
// returns a value of 50

```
[Swift Documentation](https://developer.apple.com/library/content/documentation/Swift/Conceptual/Swift_Programming_Language/Closures.html#//apple_ref/doc/uid/TP40014097-CH11-ID94)

```swift
//function type
func makeIncrementer() -> (Int -> Int) {
    func addOne(number: Int) -> Int {
        return 1 + number
    }
    return addOne
}
let increment = makeIncrementer()
increment(7)
```
[Swift Documentation](http://nilhcem.com/swift-is-like-kotlin/)

#### Java

In Java, Lambda expressions are based on instances of classes that implement functional interfaces and can be assigned to a variable.

```java
//assign lambda expression to variable
ChangeListener<Number> lambdaChangeListener = (ObservableValue<? extends Number> observable,Number oldValue, final Number newValue) -> {
    	drawGrid();
};
```

### Implementation of listeners and event handlers
#### Swift

#### Java

### Singleton
#### Swift
Lazy initialization is a technique for delaying the creation of an object or some other expensive process until it’s needed. When programming for iOS, this is helpful to make sure you utilize only the memory you need when you need it.

```swift
//singleton
class Settings {
    let user: UserSettings
    let system: SystemSettings

    static let sharedInstance = Settings()

    fileprivate init() {
        self.user = UserSettings()
        self.system = SystemSettings()
    }
}

//lazy initialization
lazy var players = [String]()
```
[Swift Lazy](http://mikebuss.com/2014/06/22/lazy-initialization-swift/)

#### Java
Singleton pattern will ensure that there is only one instance of a class is created in the Java Virtual Machine. It is used to provide global point of access to the object.
```java
//lazy initialization
public class SingletonExample {
    // Static member holds only one instance of the
    // SingletonExample class
    private static SingletonExample singletonInstance;
    // SingletonExample prevents any other class from instantiating
    private SingletonExample() {
    }
    // Providing Global point of access
    public static SingletonExample getSingletonInstance() {
        if (null == singletonInstance) {
            singletonInstance = new SingletonExample();
        }
        return singletonInstance;
    }
    public void printSingleton(){
        System.out.println("Inside print Singleton");
    }
}

//thread safe lazy initialization
public class SingletonExample {
    private static final SingletonExample singletonInstance = new SingletonExample;
    // SingletonExample prevents any other class from instantiating
    private SingletonExample() {
    }
    // Providing Global point of access
    public static SingletonExample getSingletonInstance() {
        return singletonInstance;
    }
    public void printSingleton(){
        System.out.println("Inside print Singleton");
    }
}
```
[Java Singleton](https://dzone.com/articles/singleton-design-pattern-%E2%80%93)
	
### Procedural programming
#### Swift

#### Java
	
### Functional programming
#### Swift
While Swift is not a functional language, it supports functional programming. Trailing closures are an example of functional programming in Swift.

```swift
// normal longer version
sum(from: 0, to: 10, closure: { number in return number * 10 })
// normal shorter version
sum(from: 0, to: 10, closure: { $0 * 10 })

// functional programming trailing closure longer version
sum(from: 0, to: 10) { (number) in
 return number * 10 
}
// functional programming trailing closure shorter version
sum(from: 0, to: 10) { return $0 * 10}
// functional programming trailing closure extremely short version
sum(from: 0, to: 10) { $0 * 10 } 
```
[Swift Functional Programming](https://blog.bobthedeveloper.io/no-fear-closure-in-swift-3-with-bob-part-2-1d79b8c4021d)

#### Java
Java is an Object Oriented language, but it still supports functional programming. An example of this would be a lambda expression.

```java 
this.gridPane.widthProperty().addListener((ObservableValue<? extends Number> observable, Number oldValue, final Number newValue) -> {
     drawGrid();
});
```
	
### Multithreading
#### Swift

Swift uses the `Thread` class to  have an Objective-C method run in its own thread of execution. Threads are especially useful when you need to perform a lengthy task, but don’t want it to block the execution of the rest of the application. In particular, you can use threads to avoid blocking the main thread of the application, which handles user interface and event-related actions. Threads can also be used to divide a large job into several smaller jobs, which can lead to performance increases on multi-core computers. `init()` is used to initialize an NSThread Object.

```swift
//Returns an NSThread object initialized with the given arguments
init(target: Any, selector: Selector, object: Any?)

```
[Swift Documentation](https://developer.apple.com/documentation/foundation/thread)

#### Java

Threads can be created by either extending the Thread class or implementing the Runnable interface.`start()` is used to initiate execution of a thread. `run()` serves as the path of execution for all threads. `sleep()` will make the current thread cease executing for a specified amount of time.

Java is able to write multi-threading programs, which enables you to write in a way where multiple activities can proceed concurrently in the same program. Multitasking is when multiple processes share common processing resources such as a CPU. Multi-threading extends the idea of multitasking into applications where you can subdivide specific operations within a single application into individual threads. Each of the threads can run in parallel. The OS divides processing time not only among different applications, but also among each thread within an application.
[tutorialspoint Java Multithreading](https://www.tutorialspoint.com/java/java_multithreading.htm)


```java
//implementing Runnable to create thread
public class MyRunnable implements Runnable {
  public void run() {
  // some code goes here
  }
}
//creates and starts thread
new Thread(new MyRunnable()).start(); 

//extending Thread class to create thread
class ThreadDemo extends Thread {
   private Thread t;
   private String threadName;
   
   ThreadDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }
   
   public void run() {
      //run() code
   }
   
   public void start () {
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}
```
