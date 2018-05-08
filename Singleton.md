### Singleton
#### Swift
Lazy initialization is a technique for delaying the creation of an object or some other expensive process until it’s needed. When programming for iOS, this is helpful to make sure you utilize only the memory you need when you need it.

```swift
//singleton
class Settings {
    let user: UserSettings
    let system: SystemSettings

    static let sharedInstance = Settings()

    fileprivate init() {
        self.user = UserSettings()
        self.system = SystemSettings()
    }
}

//lazy initialization
lazy var players = [String]()
```
[Swift Lazy](http://mikebuss.com/2014/06/22/lazy-initialization-swift/)

#### Java
Singleton pattern will ensure that there is only one instance of a class is created in the Java Virtual Machine. It is used to provide global point of access to the object.
```java
//lazy initialization
public class SingletonExample {
    // Static member holds only one instance of the
    // SingletonExample class
    private static SingletonExample singletonInstance;
    // SingletonExample prevents any other class from instantiating
    private SingletonExample() {
    }
    // Providing Global point of access
    public static SingletonExample getSingletonInstance() {
        if (null == singletonInstance) {
            singletonInstance = new SingletonExample();
        }
        return singletonInstance;
    }
    public void printSingleton(){
        System.out.println("Inside print Singleton");
    }
}

//thread safe lazy initialization
public class SingletonExample {
    private static final SingletonExample singletonInstance = new SingletonExample;
    // SingletonExample prevents any other class from instantiating
    private SingletonExample() {
    }
    // Providing Global point of access
    public static SingletonExample getSingletonInstance() {
        return singletonInstance;
    }
    public void printSingleton(){
        System.out.println("Inside print Singleton");
    }
}
```
[Java Singleton](https://dzone.com/articles/singleton-design-pattern-%E2%80%93)