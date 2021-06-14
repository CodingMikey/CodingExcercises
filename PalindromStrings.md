```csharp
using System;

namespace Playground
{
    class Program
    {
        static void Main(string[] args)
        {
        /// Determines whether the string is a palindrome.
        string[] array = {"civic", "Hannah", "level", "door", "open"};

        foreach(string value in array)
        {
            Console.WriteLine("{0} = {1}", value, isPalindrome(value));
        }

        }
        public static bool isPalindrome(string word)
        {
            int min = 0;
            int max = word.Length -1;
            while (true)
            {
                if(min > max)
                {
                    return true;
                }
                char a = word[min];
                char b = word[max];
                if(char.ToLower(a) != char.ToLower(b))
                {
                    return false;
                }
                min++;
                max--;

                // Console output
                // civic = True
                // Hannah = True
                // level = True 
                // door = False 
                // open = False
            }
        }
    }
}

```
