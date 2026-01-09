# Exception Handling

## Try-Catch-Finally

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.out.println("Error: " + e.getMessage());
} catch (Exception e) {
    e.printStackTrace();
} finally {
    System.out.println("Always executes");
}
```

## Exception Hierarchy

```
Throwable
├── Error (Don't catch)
└── Exception
    ├── Checked (IOException, SQLException)
    └── Unchecked (NPE, ArithmeticException)
```

## Checked vs Unchecked

```java
// Checked - Must be caught or declared
public void read() throws IOException {
    new FileInputStream("file.txt");
}

// Unchecked - Optional
public void divide(int a, int b) {
    int result = a / b;
}
```

## Custom Exceptions

```java
public class InsufficientBalanceException extends Exception {
    public InsufficientBalanceException(String msg) {
        super(msg);
    }
}

public void withdraw(double amt) throws InsufficientBalanceException {
    if (amt > balance) {
        throw new InsufficientBalanceException("Low balance");
    }
}
```

## Try-With-Resources

```java
try (FileInputStream file = new FileInputStream("file.txt")) {
    // Auto-closes resource
} catch (IOException e) {
    e.printStackTrace();
}
```

## Best Practices

- Catch specific exceptions first
- Don't suppress exceptions silently
- Log exceptions for debugging
- Use try-with-resources for cleanup
- Create custom exceptions for business logic
