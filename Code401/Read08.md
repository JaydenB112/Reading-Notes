# Notes on Collections in C#

## Arrays vs. Collections
- Arrays are suitable for working with a fixed number of strongly typed objects.
- Collections offer flexibility, allowing dynamic resizing as the application's needs change.
- Collections allow assigning a key to objects for quick retrieval.

## Using a Simple Collection (List<T>)
- `List<T>` is a generic collection that works with strongly typed lists of objects.
- Initialize a list and add elements using `List<T>`'s methods or a collection initializer.
- Iterate through a list using `foreach` or `for` statements.
- Remove elements from a list using `Remove` or `RemoveAt` methods.

## Kinds of Collections
- **System.Collections.Generic**: Provides generic collections for type-safe operations.
  - `Dictionary<TKey, TValue>`
  - `List<T>`
  - `Queue<T>`
  - `SortedList<TKey, TValue>`
  - `Stack<T>`
- **System.Collections.Concurrent**: Provides efficient thread-safe collections for concurrent access.
  - `BlockingCollection<T>`
  - `ConcurrentDictionary<TKey, TValue>`
  - `ConcurrentQueue<T>`
  - `ConcurrentStack<T>`
- **System.Collections**: Legacy classes for collections, should be avoided when possible.
  - `ArrayList`
  - `Hashtable`
  - `Queue`
  - `Stack`

## Implementing a Collection of Key/Value Pairs (Dictionary<TKey, TValue>)
- `Dictionary<TKey, TValue>` allows accessing elements by their keys.
- Use `Add` method to add elements or a collection initializer for initialization.
- Use `ContainsKey` or `TryGetValue` methods to check if a key exists and retrieve its associated value.

## Using LINQ to Access a Collection
- LINQ (Language-Integrated Query) provides querying capabilities for collections.
- Use LINQ queries to filter, order, and group elements.
- LINQ queries return different collections containing the query results.

## Sorting a Collection
- Implement the `IComparable<T>` interface to enable sorting on custom objects.
- Use the `Sort` method on a `List<T>` to automatically call `CompareTo` method for sorting.

## Defining a Custom Collection
- Implement `IEnumerable<T>` or `IEnumerable` to define a custom collection.
- Prefer using built-in collections over defining custom collections.

## Iterators
- Iterators enable custom iteration over a collection.
- Use the `yield return` statement inside an iterator method to return elements one at a time.
- Iterators are called by using `foreach` loops.

Note: The examples in the article demonstrate the concepts described for each topic using C# code snippets.
