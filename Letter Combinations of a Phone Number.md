Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.

A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

Example 1:

Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
Example 2:

Input: digits = ""
Output: []
Example 3:

Input: digits = "2"
Output: ["a","b","c"]

```csharp
public IList<string> LetterCombinations(string digits)
        {
            if (digits == null || digits.Length == 0)
                return new List<string>();

            Hashtable hash = new Hashtable();
            char[][] graph = new char[digits.Length][];
            string temp = string.Empty;
            List<string> result = new List<string>();

            hash.Add('2', "abc");
            hash.Add('3', "def");
            hash.Add('4', "ghi");
            hash.Add('5', "jkl");
            hash.Add('6', "mno");
            hash.Add('7', "pqrs");
            hash.Add('8', "tuv");
            hash.Add('9', "wxyz");

            for (int i = 0; i < digits.Length; i++)
            {
                temp = (string)hash[digits[i]];

                graph[i] = new char[temp.Length];

                for (int j = 0; j < temp.Length; j++)
                    graph[i][j] = temp[j];
            }

            DFS(graph, 0, string.Empty, result);

            return result;
        }

        public void DFS(char[][] graph, int currentLayer, string previousCombination, List<string> result)
        {
            string currentCombination = string.Empty;

            if (graph.Length - 1 < currentLayer)
            {
                result.Add(previousCombination);
                return;
            }

            foreach (var item in graph[currentLayer])
            {
                currentCombination = previousCombination;

                DFS(graph, currentLayer + 1, currentCombination += item, result);
            }
        }
```
