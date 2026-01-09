# Multithreading & Concurrency

## Creating Threads

### Extend Thread
```java
class MyThread extends Thread {
    public void run() { System.out.println("Running"); }
}
new MyThread().start();
```

### Implement Runnable
```java
Thread t = new Thread(() -> System.out.println("Running"));
t.start();
```

## Synchronization

```java
public synchronized void increment() { count++; }

synchronized(this) { count++; }
```

## Thread States
- NEW, RUNNABLE, BLOCKED, WAITING, TIMED_WAITING, TERMINATED

## Wait & Notify
```java
synchronized(obj) {
    while (!condition) obj.wait();
    obj.notifyAll();
}
```

## Executor Framework
```java
ExecutorService executor = Executors.newFixedThreadPool(5);
executor.execute(() -> System.out.println("Task"));
executor.shutdown();
```
