### Implementation of listeners and event handlers
#### Swift
The Event class has a generic parameter T which defines the type of data that this event conveys and the EventHandler typealias declares a function that accepts this type. The event class contains an array of handlers that are instances of EventHandlerWrapper that implement an Invocable protocol.

```swift
public class Event<T> {

  public typealias EventHandler = T -> ()

  private var eventHandlers = [Invocable]()

  public func raise(data: T) {
  for handler in self.eventHandlers {
    handler.invoke(data)
    }
  }

  public func addHandler<U: AnyObject>(target: U,
            handler: (U) -> EventHandler) -> Disposable {
    let wrapper = EventHandlerWrapper(target: target,
                         handler: handler, event: self)
    eventHandlers.append(wrapper)
    return wrapper
  }
}

private protocol Invocable: class {
  func invoke(data: Any)
}
```
[Implementing Events in Swift](http://blog.scottlogic.com/2015/02/05/swift-events.html)

#### Java
An event is used to inform a listener that something has happened to a component in the GUI. It includes all of the information that a listener needs to figure out what happened and to whom it happened (the what and who of the event). An event must give enough information to fully describe itself.
[Javaworld Events and listeners](https://www.javaworld.com/article/2077351/java-se/events-and-listeners.html)

A common event listener is the ChangeListener. A ChangeListener is notified whenever the value of an ObservableValue changes
[Java Documentation](https://docs.oracle.com/javase/8/javafx/api/javafx/beans/value/ChangeListener.html)

```java
ChangeListener<Number> changeListener = new ChangeListener<Number>() {
     @Override 
     public void changed(ObservableValue< ? extends Number> observable, Number oldValue, final Number newValue) {
          drawGrid();
     } 
};
this.gridPane.widthProperty().addListener(changeListener);
```