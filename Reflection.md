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