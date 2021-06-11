## Stack Data Structure Sample 🔧
```csharp
using System;
using System.Collections;

namespace DataStructuresAndAlgorithms
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creates and initializes a new Stack
            Stack myStack = new Stack();
            myStack.Push("Hello");
            myStack.Push("World");
            myStack.Push("!");

            // Displays the properties and values of the Stack
            Console.WriteLine("myStack");
            Console.WriteLine("\tCount: {0}", myStack.Count);
            Console.Write("\tValues: ");
            PrintValues(myStack);

            // Display the properties and values of Stack after Pop
            myStack.Pop();
            Console.WriteLine("myStack after Pop");
            Console.WriteLine("\tCount: {0}", myStack.Count);
            Console.Write("\tValues: ");
            PrintValues(myStack);

            // Display the properties and values of Stack after Clear
            myStack.Clear();
            Console.WriteLine("myStack after Clear");
            Console.WriteLine("\tCount: {0}", myStack.Count);
            Console.Write("\tValues: ");
            PrintValues(myStack);
        }

        public static void PrintValues(IEnumerable myCollection)
        {
            foreach (Object obj in myCollection)
                Console.Write("{0}", obj);
            Console.WriteLine();
        }

        /*
        This code produces the following output.
        myStack
        Count: 3
        Values: !WorldHello

        myStack after Pop
                Count: 2
                Values: WorldHello

        myStack after Clear
                Count: 0
                Values:
        */

    }
}

```
