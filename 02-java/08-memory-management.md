# Memory Management & Garbage Collection

## JVM Memory Structure

```
Heap (Shared, GC managed)
├── Young Generation
│   ├── Eden Space
│   └── Survivor Spaces (S0, S1)
└── Old Generation

Stack (Per-thread)
├── Local variables
├── Method calls
└── References

Metaspace
├── Class definitions
├── Method code
└── Runtime data
```

## Garbage Collection

### Generational GC
- Most objects die young
- Young generation collected frequently (Minor GC)
- Old generation collected rarely (Major GC)

```java
// Object lifecycle
Object obj = new Object();  // Allocated in Eden
// ... used ...
obj = null;                 // Eligible for GC
```

## GC Algorithms

1. **Mark-Sweep**: Mark live objects, sweep dead ones
2. **Mark-Compact**: Mark, then compact live objects
3. **Copy**: Copy live objects to new region

## Memory Leaks

```java
// Memory leak - list grows indefinitely
public class MemoryLeak {
    static List<Object> list = new ArrayList<>();
    
    public void add() {
        list.add(new Object());  // Never removed
    }
}

// Better approach
public class NoLeak {
    List<Object> list = new ArrayList<>();  // Instance scoped
}
```

## Best Practices

- Nullify references when done: `obj = null`
- Avoid static collections with unbounded growth
- Close resources: try-with-resources
- Use WeakReference for cache-like structures
- Monitor with jvisualvm, jconsole

## GC Tuning Parameters

```bash
-Xms4g              # Initial heap size
-Xmx8g              # Max heap size
-XX:+UseG1GC        # Use G1 garbage collector
-XX:MaxGCPauseMillis=200
-XX:+PrintGCDetails # Log GC events
```

## Strong vs Weak References

```java
// Strong - not eligible for GC
Object obj = new Object();

// Weak - eligible even if referenced
WeakReference<Object> weak = new WeakReference<>(obj);

// Soft - eligible only if memory low
SoftReference<Object> soft = new SoftReference<>(obj);
```
