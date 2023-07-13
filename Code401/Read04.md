# Properties in C#

A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field. Properties can be used as if they're public data members, but they're special methods called accessors. This feature enables data to be accessed easily and still helps promote the safety and flexibility of methods.

## Properties Overview

- Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.
- Properties have get and set accessors (and in C# 9 and later, init accessors) to retrieve and assign values.
- Properties can be read-write, read-only, or write-only.
- Simple properties can be implemented using expression body definitions or auto-implemented properties.
- Properties can have backing fields for storing values.

## Properties with Backing Fields

One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value. The get accessor returns the value of the private field, and the set accessor may perform data validation or computations before assigning a value to the private field.

```csharp
public class TimePeriod
{
    private double _seconds;

    public double Hours
    {
        get { return _seconds / 3600; }
        set
        {
            if (value < 0 || value > 24)
                throw new ArgumentOutOfRangeException(nameof(value), "The valid range is between 0 and 24.");

            _seconds = value * 3600;
        }
    }
}
``````



## Memory Management in .NET: Stack vs Heap

### Introduction

Memory management and garbage collection (GC) are essential aspects to consider for optimizing application performance in the .NET framework. Understanding memory management also provides insights into variable behavior. In this journal article, we will delve into the basics of the Stack and Heap, different variable types, and explore why variables behave the way they do.

### Stack vs. Heap: What's the Difference?

The Stack is responsible for tracking code execution or method calls, while the Heap is responsible for managing objects and data. The Stack resembles a stack of boxes, where each box represents a method call. Only the top box on the stack is accessible, and once it's no longer needed, it is discarded. On the other hand, the Heap is like a heap of clean laundry on a bed. It holds information that can be accessed at any time without constraints. To access objects in the Stack, we must remove the top box, whereas objects in the Heap can be quickly accessed.

### Understanding What Goes on the Stack and Heap

1. Value Types: Value types include primitive types such as bool, byte, char, decimal, double, enum, float, int, long, sbyte, short, struct, uint, ulong, and ushort. These types are stored in the Stack.

2. Reference Types: Reference types include class, interface, delegate, object, and string. These types are stored in the Heap. Reference types are accessed through pointers, which are chunks of memory pointing to another space in memory. Unlike Stack, there are no constraints on accessing Heap objects.

3. Pointers: Pointers, also known as references, are managed by the Common Language Runtime (CLR). They are different from reference types in that they are used to access reference types. Pointers store memory addresses or null values.

4. Instructions: Instructions refer to the execution steps in our code. They are part of the memory management but will be explained later.

### Placement of Variables: Stack vs. Heap

To determine where variables are stored, follow these rules:

1. Reference Types always go on the Heap.
2. Value Types and Pointers go where they are declared.

The Stack is responsible for tracking thread execution and holds method parameters and local variables. Each thread has its own stack. When a method is called, its parameters are placed on the stack. Value types declared within a method are also placed on the stack. However, if a value type is declared within a reference type, it will be placed within the reference type on the Heap.

Example:
```C#
public int AddFive(int pValue)
{
    int result;
    result = pValue + 5;
    return result;
}
