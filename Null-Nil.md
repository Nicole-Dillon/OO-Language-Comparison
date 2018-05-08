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