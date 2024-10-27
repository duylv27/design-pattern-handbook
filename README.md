### Design Patterns
## Behavioral Design Pattern
- **Template Method**: defines the skeleton of an algorithm in a method, allowing subclasses to alter certain steps of the algorithm without changing its structure. This pattern promotes code reuse and helps implement invariant parts of an algorithm in a base class while allowing flexibility through subclassing.
- **Strategy**: defines a family of algorithms, encapsulates each algorithm in a class, and makes them interchangeable. The strategy pattern allows the algorithm to vary independently from the client that uses it. It is commonly used to replace conditional logic with different strategies.

## Creational Design Pattern
- **Factory Method**: Utilizing the Factory Method design pattern for creating objects.
- **Singleton**:
  - **Lazy Initialization**: Implementing Singleton with lazy initialization and thread safety using `synchronized`. Performance considerations due to `synchronized`. (eager or lazy init).
  ```java
      public static synchronized LazySingleton getInstance() {
        if (instance == null) {
            instance = new LazySingleton();
        }
        return instance;
    }
  ```
  - **Bill Pugh Singleton**: Creating a Singleton using a nested static helper class. Utilizes `static` functionality managed by the JVM. (lazy init).
  ```java
  public class BillPughSingleton {
    private BillPughSingleton() {
        // private constructor to prevent instantiation
    }

    private static class SingletonHelper {
        private static final BillPughSingleton INSTANCE = new BillPughSingleton();
    }

    public static BillPughSingleton getInstance() {
        return SingletonHelper.INSTANCE;
    }
  }
  ```
  - **Enum Singleton**:
    - **Thread Safety**: Ensured by the JVM, no additional thread safety required.
    - **Reflection Safety**: Prevents reflection from breaking the Singleton pattern.
    - **Serialization Safety**: Ensures safe serialization of the Singleton instance.
  - **Singleton object with serializaion/deserialization** >> search for `readResolve`
