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