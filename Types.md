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