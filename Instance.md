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