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