### Multithreading
#### Swift

Swift uses the `Thread` class to  have an Objective-C method run in its own thread of execution. Threads are especially useful when you need to perform a lengthy task, but don’t want it to block the execution of the rest of the application. In particular, you can use threads to avoid blocking the main thread of the application, which handles user interface and event-related actions. Threads can also be used to divide a large job into several smaller jobs, which can lead to performance increases on multi-core computers. `init()` is used to initialize an NSThread Object.

```swift
//Returns an NSThread object initialized with the given arguments
init(target: Any, selector: Selector, object: Any?)

```
[Swift Documentation](https://developer.apple.com/documentation/foundation/thread)

Swift now uses Grand Central Display (GCD) to simplify work with systems with multi-core processors. GCD’s task parallelism is based on the thread pool pattern. Multiple threads are always available, waiting for tasks to be executed concurrently. Dispatch queues manages tasks in FIFO order. Multitasking is accomplished using concurrent queues. Concurrent queues execute one or more tasks concurrently and are completed according to complexity and not by the order in the queue. Dispatch queues are thread safe. They can be accessed from different threads simultaneously without locking. Developers can use dispatch queues to make their own code thread safe.

[Swift GCD](https://medium.com/modernnerd-code/grand-central-dispatch-crash-course-for-swift-3-8bf2652c1cb8)

```swift
dispatch_async(dispatch_get_global_queue(DISPATCH_QUEUE_PRIORITY_DEFAULT, 0)) {  
    // Download file or perform expensive task

    dispatch_async(dispatch_get_main_queue()) {  
        // Update the UI  
    }
}
```
[GCD:Multithreading](https://learnappmaking.com/grand-central-dispatch-swift/)

#### Java

Threads can be created by either extending the Thread class or implementing the Runnable interface.`start()` is used to initiate execution of a thread. `run()` serves as the path of execution for all threads. `sleep()` will make the current thread cease executing for a specified amount of time.

Java is able to write multi-threading programs, which enables you to write in a way where multiple activities can proceed concurrently in the same program. Multitasking is when multiple processes share common processing resources such as a CPU. Multi-threading extends the idea of multitasking into applications where you can subdivide specific operations within a single application into individual threads. Each of the threads can run in parallel. The OS divides processing time not only among different applications, but also among each thread within an application.

```java
//implementing Runnable to create thread
public class MyRunnable implements Runnable {
  public void run() {
  // some code goes here
  }
}
//creates and starts thread
new Thread(new MyRunnable()).start(); 

//extending Thread class to create thread
class ThreadDemo extends Thread {
   private Thread t;
   private String threadName;
   
   ThreadDemo( String name) {
      threadName = name;
      System.out.println("Creating " +  threadName );
   }
   
   public void run() {
      //run() code
   }
   
   public void start () {
      if (t == null) {
         t = new Thread (this, threadName);
         t.start ();
      }
   }
}
```
[tutorialspoint Java Multithreading](https://www.tutorialspoint.com/java/java_multithreading.htm)