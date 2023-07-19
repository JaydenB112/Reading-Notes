Inheritance, together with encapsulation and polymorphism, is one of the three primary characteristics of object-oriented programming. Inheritance enables you to create new classes that reuse, extend, and modify the behavior defined in other classes. The class whose members are inherited is called the base class, and the class that inherits those members is called the derived class. A derived class can have only one direct base class. However, inheritance is transitive. If ClassC is derived from ClassB, and ClassB is derived from ClassA, ClassC inherits the members declared in ClassB and ClassA.

> Note: Structs do not support inheritance, but they can implement interfaces.

Conceptually, a derived class is a specialization of the base class. For example, if you have a base class Animal, you might have one derived class that is named Mammal and another derived class that is named Reptile. A Mammal is an Animal, and a Reptile is an Animal, but each derived class represents different specializations of the base class.

Interface declarations may define a default implementation for its members. These implementations are inherited by derived interfaces and by classes that implement those interfaces. For more information on default interface methods, see the article on interfaces.

When you define a class to derive from another class, the derived class implicitly gains all the members of the base class, except for its constructors and finalizers. The derived class reuses the code in the base class without having to reimplement it. You can add more members in the derived class. The derived class extends the functionality of the base class.

The following illustration shows a class WorkItem that represents an item of work in some business process. Like all classes, it derives from System.Object and inherits all its methods. WorkItem adds six members of its own. These members include a constructor because constructors aren't inherited. Class ChangeRequest inherits from WorkItem and represents a particular kind of work item. ChangeRequest adds two more members to the members that it inherits from WorkItem and from Object. It must add its own constructor, and it also adds originalItemID. Property originalItemID enables the ChangeRequest instance to be associated with the original WorkItem to which the change request applies.

![Diagram that shows class inheritance](image-url-here)

The following example shows how the class relationships demonstrated in the previous illustration are expressed in C#. The example also shows how WorkItem overrides the virtual method Object.ToString and how the ChangeRequest class inherits the WorkItem implementation of the method. The first block defines the classes:

```csharp
// WorkItem implicitly inherits from the Object class.
public class WorkItem
{
    // Class implementation here...
}

// ChangeRequest derives from WorkItem and adds a property (originalItemID) and two constructors.
public class ChangeRequest : WorkItem
{
    // Class implementation here...
}
``````


# Reading Notes

## Polymorphism in Object-Oriented Programming

Polymorphism is often referred to as the third pillar of object-oriented programming, following encapsulation and inheritance. It has two distinct aspects:

1. **Runtime Polymorphism:** At runtime, objects of a derived class can be treated as objects of a base class in method parameters, collections, or arrays. This allows flexibility in working with different types of objects without explicitly knowing their specific types at compile time.

2. **Virtual Methods:** Base classes can define and implement virtual methods, which derived classes can override. This allows derived classes to provide their own implementation of a method while still maintaining a common interface. At runtime, when a virtual method is called, the overridden version in the derived class is invoked.

Virtual methods enable the use of polymorphism to work with groups of related objects in a uniform way. For example, in a drawing application, you can have a base class called `Shape` and derived classes like `Rectangle`, `Circle`, and `Triangle`. Each derived class can override the virtual `Draw` method to draw the specific shape it represents. By treating all shapes as `Shape` objects, you can call the `Draw` method on each object without knowing the specific type of the shape.

Polymorphism allows for code reuse, extensibility, and flexibility in object-oriented programming. It enables you to work with objects of different types in a uniform manner and provides the ability to customize behavior in derived classes while maintaining a common interface.
