```csharp
using System;

namespace Playground
{
    class Program
    {
        static void Main(string[] args)
        {
            string value1 = RemoveDuplicateChars("Hello");
            string value2 = RemoveDuplicateChars("Goodbye");
            string value3 = RemoveDuplicateChars("Tomorrow");
            string value4 = RemoveDuplicateChars("Test");

            Console.WriteLine(value1);
            Console.WriteLine(value2);
            Console.WriteLine(value3);
            Console.WriteLine(value4);
            
        }
        static string RemoveDuplicateChars(string key)
        {
            // Store encountered letters in this string.
            string table = "";
            // Store the result in this string.
            string result = "";

            // Loop over each character.
            foreach(char value in key)
            {
                // See if character is in the table.
                if(table.IndexOf(value) == -1) 
                {
                    // Append to the table and the result.
                    table += value;
                    result += value;
                }
            }
            return result;
        }
    }
}

```
