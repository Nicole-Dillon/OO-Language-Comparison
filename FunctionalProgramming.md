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