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