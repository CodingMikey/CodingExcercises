```csharp
using System;

namespace Playground
{
    class Program
    {
        static void Main(string[] args)
        {
            /*
            Two words are said to be Anagrams of each other if they share the same set of 
            letters to form the respective words.for an example: Silent–>Listen, post–>opts.
            */

            // Recieve words from user
            Console.WriteLine("Enter first word:");
            string word1 = Console.ReadLine();
            Console.WriteLine("Enter second word");
            string word2 = Console.ReadLine();

            // Step 1 convert strings into char arrays
            char[] char1 = word1.ToLower().ToCharArray();
            char[] char2 = word2.ToLower().ToCharArray();

            // Step 2 sort the char arrays
            Array.Sort(char1);
            Array.Sort(char2);

            // Step 3 
            string NewWord1 = new string(char1);
            string NewWord2 = new string(char2);

            //Step 4  
            //ToLower allows to compare the words in same case, in this case, lower case.  
            //ToUpper will also do exact same thing in this context  
            if (NewWord1 == NewWord2)  
            {  
                Console.WriteLine("Yes! Words \"{0}\" and \"{1}\" are Anagrams", word1, word2);  
            }  
            else  
            {  
                Console.WriteLine("No! Words \"{0}\" and \"{1}\" are not Anagrams", word1, word2);  
            } 
            Console.ReadLine(); 

            /*
            Output: Enter first word:
            silent
            Enter second word
            listen
            Yes! Words "silent" and "listen" are Anagrams

            */
        }
    }
}

```
