# Java 8+ Features

## Lambda Expressions

```java
// Old way
Runnable r = new Runnable() {
    public void run() { System.out.println("Hello"); }
};

// Lambda way
Runnable r = () -> System.out.println("Hello");

// With parameters
Comparator<Integer> comp = (a, b) -> a - b;
```

## Functional Interfaces

```java
@FunctionalInterface
public interface Calculator {
    int calculate(int a, int b);
}

// Usage
Calculator add = (a, b) -> a + b;
Calculator multiply = (a, b) -> a * b;
```

## Default Methods

```java
public interface Logger {
    void log(String msg);
    
    default void error(String msg) {
        System.err.println("ERROR: " + msg);
    }
}
```

## Method References

```java
List<String> names = Arrays.asList("Danish", "Khan");

// Lambda
names.forEach(s -> System.out.println(s));

// Method reference
names.forEach(System.out::println);

// Static method reference
names.stream().map(String::toUpperCase);
```

## Optional

```java
Optional<String> opt = Optional.of("value");

opt.ifPresent(System.out::println);
String result = opt.orElse("default");
String result2 = opt.orElseThrow(() -> new Exception("Not found"));
```

## Predicates & Consumers

```java
Predicate<Integer> isPositive = n -> n > 0;
boolean result = isPositive.test(5);  // true

Consumer<String> printer = s -> System.out.println(s);
printer.accept("Hello");

Function<Integer, Integer> square = n -> n * n;
int result = square.apply(5);  // 25
```
