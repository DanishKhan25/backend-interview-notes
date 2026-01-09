# Streams & Lambda Expressions

## Stream Basics

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

// Filter, map, collect
List<Integer> evens = numbers.stream()
    .filter(n -> n % 2 == 0)
    .collect(Collectors.toList());

// Map and transform
List<Integer> squared = numbers.stream()
    .map(n -> n * n)
    .collect(Collectors.toList());
```

## Intermediate Operations

```java
stream.filter(predicate)        // Keep matching
stream.map(function)            // Transform
stream.flatMap(function)        // Flatten nested streams
stream.distinct()               // Remove duplicates
stream.sorted()                 // Sort elements
stream.limit(n)                 // Take first n
stream.skip(n)                  // Skip first n
```

## Terminal Operations

```java
// Collectors
stream.collect(Collectors.toList());
stream.collect(Collectors.toSet());
stream.collect(Collectors.joining(","));
stream.collect(Collectors.groupingBy(e -> e.getType()));

// Other terminals
stream.forEach(System.out::println);
stream.reduce((a, b) -> a + b);
stream.count();
stream.anyMatch(predicate);
stream.allMatch(predicate);
stream.findFirst();
```

## Reduce Operation

```java
Integer sum = numbers.stream()
    .reduce(0, (a, b) -> a + b);

Optional<Integer> product = numbers.stream()
    .reduce((a, b) -> a * b);
```

## Parallel Streams

```java
List<Integer> result = numbers.parallelStream()
    .filter(n -> n > 0)
    .map(n -> n * 2)
    .collect(Collectors.toList());
```

## Common Stream Patterns

```java
// Sort and limit
names.stream()
    .sorted()
    .limit(5)
    .forEach(System.out::println);

// Group by
Map<String, List<Person>> byCity = people.stream()
    .collect(Collectors.groupingBy(Person::getCity));

// Count occurrences
Map<String, Long> counts = words.stream()
    .collect(Collectors.groupingBy(w -> w, Collectors.counting()));
```
