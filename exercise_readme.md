1.  Write a program and ask the user to enter their name. Use an array to reverse the name and then store the result in a new string. Display the reversed name on the console.

**program.cs**

```C#

    string userName = Console.ReadLine();

    // split the word to each charcters
    char[] charArray = userName.ToCharArray();
    // reverse the array
    Array.Reverse(charArray);
    // join array > string
    string output = String.Join(" ", charArray);
    Console.WriteLine(output);
```

2. Write a program and ask the user to enter 5 numbers. If a number has been previously entered, display an error message and ask the user to re-try. Once the user successfully enters 5 unique numbers, sort them and display the result on the console.

**ProgramTwo.cs**

```C#

using System;
using System.Collections.Generic;
using System.Text;

namespace ArrayListExercise
{
    class ProgramTwo
    {
        public void Result()
        {
            var numbersList = new int[5];
            Console.WriteLine("Enter 5 unique numbers");
            for (int i = 0; i < 5; i++)
            {
                var newVal = Convert.ToInt32(Console.ReadLine());

                // find index of new value
                var currentValIndex = Array.IndexOf(numbersList, newVal);

                // since value not present, currentValIndex gives -1
                if (currentValIndex == -1)
                {
                    numbersList[i] = newVal;
                }
                else
                {
                    throw new Exception($"{newVal} exists in {numbersList}");
                }
            }
            Array.Sort(numbersList);
            foreach(int a in numbersList)
            {
                Console.WriteLine(a);
            }

        }

    }
}

```

**Program.cs**

```C#

    // acess programTwo class
    var c = new ProgramTwo();
    c.Result();
```

3. Write a program and ask the user to continuously enter a number or type "Quit" to exit. The list of numbers may include duplicates. Display the unique numbers that the user has entered.

**Program.cs**

```C#
 static void Main(string[] args)
        {

            List<int> dataList = new List<int>();
            var value = Console.ReadLine();

            while(value != "quit")
            {
                var valueNew = Convert.ToInt32(value);
                dataList.Add(valueNew);
                value = Console.ReadLine();
            }

            // return distinct element from list and convert to array
            int[] s = dataList.Distinct().ToArray();
            foreach (var d in s)
            {
                Console.WriteLine(d);
            }


        }

```

---
