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