## Interfaces - Define Behavior for Multiple Types

An interface contains definitions for a group of related functionalities that a non-abstract class or a struct must implement. Interfaces can include instance methods, properties, events, indexers, or any combination of those member types. They may also contain static constructors, fields, constants, or operators. However, interfaces cannot declare instance data such as fields, auto-implemented properties, or property-like events.

Using interfaces allows you to include behavior from multiple sources in a class, which is particularly important in C# since the language doesn't support multiple inheritance of classes. Additionally, interfaces are necessary for simulating inheritance for structs since structs cannot directly inherit from another struct or class.

You define an interface using the `interface` keyword, as shown in the example below:

```csharp
interface IEquatable<T>
{
    bool Equals(T obj);
}
``````


# Notes on the Value and Usage of Interfaces

## Problem Interfaces Solve
- Interfaces separate how we use something from how it is implemented.
- They allow code to work with various implementations of a set of responsibilities without handling each one explicitly.
- For example, a `Driver` class should use an `IDriveable` interface to drive any car, boat, or other vehicle.

## Interfaces as Contracts
- Interfaces specify that a class meets certain expectations, defining a contract for other classes to rely on.
- A class implementing an interface does not mean it "is" the interface; rather, it "implements" the interface.
- A class can implement multiple interfaces, as each interface addresses a specific contract.

## Interfaces Are Always Implemented by More Than One Class
- Interfaces should be used to solve actual problems, not created in anticipation of future needs (YAGNI - You Ain't Gonna Need It).
- The ratio of interfaces to classes implementing them should be close to 1:1, indicating actual problem-solving usage.
- Interfaces should be introduced when we have multiple classes needing to fulfill a particular contract.

## Testing and Dependency Injection
- Interfaces are sometimes abused to facilitate unit testing and dependency injection.
- Using interfaces solely for mocking and dependency injection creates unnecessary indirection and coupling.
- Dependency injection's real benefit lies in controlling the implementation of an interface at runtime.

## Language-Supported Seams
- Instead of relying on interfaces as a workaround, a language-supported mechanism is needed to replace concrete class implementations at runtime.
- Creating interfaces only for testing and dependency injection dilutes the true purpose of interfaces.

**Conclusion**
- Proper use of interfaces involves solving actual problems where multiple classes need to fulfill a contract.
- Avoid creating interfaces preemptively and abusing them for testing or dependency injection purposes.
- Focus on reducing dependencies and splitting classes to achieve cleaner code without excessive interface usage.
