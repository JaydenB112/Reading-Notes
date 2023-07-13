# File and Stream I/O in .NET

File and stream I/O (input/output) involves the transfer of data to or from a storage medium. In .NET, the System.IO namespaces provide types for reading and writing data streams and files, supporting both synchronous and asynchronous operations. These namespaces also include types for compression, decompression, and communication through pipes and serial ports.

## Files and Directories

- The System.IO namespace provides types for interacting with files and directories.
- You can get and set properties, retrieve collections, and perform operations such as creating, copying, deleting, and moving files and directories.
- Use classes like `File`, `FileInfo`, `Directory`, `DirectoryInfo`, and `Path` for working with file and directory paths.

## Streams

- Streams are sequences of bytes used for reading from and writing to a backing store.
- The abstract base class `Stream` supports reading, writing, and seeking operations.
- Derived classes like `FileStream`, `MemoryStream`, `NetworkStream`, and `PipeStream` provide different stream implementations.
- Streams involve reading, writing, and seeking operations, with capabilities determined by the stream type.

## Readers and Writers

- The System.IO namespace also provides reader and writer types for working with encoded characters.
- These types handle the conversion of characters to and from bytes in order to read from or write to streams.
- Commonly used classes include `BinaryReader`, `BinaryWriter`, `StreamReader`, `StreamWriter`, `StringReader`, `StringWriter`, `TextReader`, and `TextWriter`.

## Asynchronous I/O Operations

- Asynchronous I/O is recommended for resource-intensive operations to keep the application responsive.
- Use methods with the `Async` suffix like `ReadAsync`, `WriteAsync`, `CopyToAsync`, and `FlushAsync`.
- Asynchronous I/O operations can be performed using the `async` and `await` keywords.

## Compression

- The System.IO.Compression namespace contains types for compressing and decompressing files and streams.
- Classes like `ZipArchive`, `ZipArchiveEntry`, `ZipFile`, `DeflateStream`, and `GZipStream` are commonly used for compression tasks.

## Isolated Storage

- Isolated storage provides a mechanism for storing data with isolation and safety.
- It offers a virtual file system isolated by user, assembly, and domain.
- Isolated storage is useful when an application lacks permission to access user files.
- For Windows 8.x Store apps, use the `Windows.Storage` namespace instead of isolated storage.

## I/O Operations in Windows Store Apps

- .NET for Windows 8.x Store apps includes types for reading from and writing to streams.
- Some differences exist compared to traditional .NET I/O, such as the absence of file-related types and the need for asynchronous methods.
- Use the `Windows.Storage` namespace for file operations and `Windows.Storage.Compression` for compression in Windows 8.x Store apps.

## I/O and Security

- When using the System.IO classes, adhere to operating system security requirements such as access control lists (ACLs) to control file and directory access.
- Default security policies restrict Internet or intranet applications from accessing files on a user's computer.
- Use isolated storage for .NET applications intended for download over the internet or intranet.
- Be cautious when passing streams to less-trusted code or application domains.



# Writing Text to a File in .NET

This article demonstrates different ways to write text to a file in a .NET application. The following classes and methods are commonly used for this purpose:

- `StreamWriter`: Contains methods for synchronously (`Write` and `WriteLine`) or asynchronously (`WriteAsync` and `WriteLineAsync`) writing text to a file.
- `File`: Provides static methods for writing text to a file (`WriteAllLines`, `WriteAllText`) or appending text to a file (`AppendAllLines`, `AppendAllText`, `AppendText`).
- `Path`: Used for manipulating file and directory paths, including methods like `Combine`, `Join`, and `TryJoin`.

## Example: Synchronously Write Text with `StreamWriter`

The following example demonstrates how to use the `StreamWriter` class to synchronously write text to a new file line by line. The `StreamWriter` object is declared and instantiated within a `using` statement, ensuring that the stream is flushed and closed automatically.

```csharp
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {
        string[] lines = { "First line", "Second line", "Third line" };
        string docPath = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

        using (StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "WriteLines.txt")))
        {
            foreach (string line in lines)
                outputFile.WriteLine(line);
        }
    }
}

# Writing and Reading Data with BinaryWriter and BinaryReader



The example creates a data file called `Test.data` in the current directory, creates the associated `BinaryWriter` and `BinaryReader` objects, and uses the `BinaryWriter` object to write the integers 0 through 10 to `Test.data`, leaving the file pointer at the end of the file. The `BinaryReader` object then sets the file pointer back to the beginning and reads out the specified content.

.

```csharp
using System;
using System.IO;

class MyStream
{
    private const string FILE_NAME = "Test.data";

    public static void Main()
    {
        if (File.Exists(FILE_NAME))
        {
            Console.WriteLine($"{FILE_NAME} already exists!");
            return;
        }

        using (FileStream fs = new FileStream(FILE_NAME, FileMode.CreateNew))
        {
            using (BinaryWriter w = new BinaryWriter(fs))
            {
                for (int i = 0; i < 11; i++)
                {
                    w.Write(i);
                }
            }
        }

        using (FileStream fs = new FileStream(FILE_NAME, FileMode.Open, FileAccess.Read))
        {
            using (BinaryReader r = new BinaryReader(fs))
            {
                for (int i = 0; i < 11; i++)
                {
                    Console.WriteLine(r.ReadInt32());
                }
            }
        }
    }
}
