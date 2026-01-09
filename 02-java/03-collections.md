# Collections Framework

> Core data structures for managing groups of objects

## Collection Hierarchy

```
Iterable
    |
 Collection
    |
    +--List (Ordered, allows duplicates)
    |   ├-- ArrayList
    |   ├-- LinkedList
    |   └-- Vector
    |
    +--Set (Unique elements, unordered)
    |   ├-- HashSet
    |   ├-- LinkedHashSet
    |   └-- TreeSet
    |
    +--Queue (FIFO)
        ├-- PriorityQueue
        └-- Deque

Map (Key-Value pairs)
    ├-- HashMap
    ├-- LinkedHashMap
    ├-- TreeMap
    └-- Hashtable
```

## Lists

```java
// ArrayList - Dynamic array
List<String> fruits = new ArrayList<>();
fruits.add("Apple");
fruits.add("Banana");
fruits.add(0, "Mango");  // Insert at index 0
fruits.remove(1);
System.out.println(fruits.get(0));

// LinkedList - Doubly linked list
LinkedList<Integer> numbers = new LinkedList<>();
numbers.add(1);
numbers.addFirst(0);
numbers.addLast(2);
numbers.removeFirst();
```

## Sets

```java
// HashSet - Unique, unordered
Set<String> uniqueNames = new HashSet<>();
uniqueNames.add("Danish");
uniqueNames.add("Khan");
uniqueNames.add("Danish");  // Won't be added

// TreeSet - Sorted
Set<Integer> sorted = new TreeSet<>();
sorted.add(5);
sorted.add(2);
sorted.add(8);
System.out.println(sorted);  // [2, 5, 8]
```

## Maps

```java
// HashMap - Key-value pairs
Map<String, Integer> ages = new HashMap<>();
ages.put("Danish", 30);
ages.put("Khan", 25);
ages.get("Danish");         // 30
ages.containsKey("Danish");  // true
ages.remove("Khan");

// Iterating
for (String key : ages.keySet()) {
    System.out.println(key + " -> " + ages.get(key));
}
```

## Queues

```java
// Queue - FIFO
Queue<Integer> queue = new LinkedList<>();
queue.add(1);
queue.add(2);
queue.offer(3);          // Add to end
queue.poll();            // Remove from front
queue.peek();            // View front
```

## Key Differences

| Feature | ArrayList | LinkedList | HashSet | TreeSet |
|---------|-----------|-----------|---------|----------|
| Order | Insertion | Insertion | None | Sorted |
| Access | O(1) | O(n) | O(1) | O(log n) |
| Insert/Delete | O(n) | O(1) | O(1) | O(log n) |
| Duplicates | Yes | Yes | No | No |

## Common Methods

```java
List<String> list = new ArrayList<>();
list.add("A");
list.size();
list.isEmpty();
list.contains("A");
list.clear();
Collections.sort(list);
Collections.reverse(list);
Collections.shuffle(list);
```
