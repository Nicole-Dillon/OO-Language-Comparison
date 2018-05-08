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