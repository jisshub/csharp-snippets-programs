# Files

- C# includes static File class to perform I/O operation on physical file system. The static File class includes various utility method to interact with physical file of any type e.g. binary, text etc.

- methods are invoked on File class directly, and not on instance methods.

## Demo

```C#
class Program
    {
        static void Main(string[] args)
        {
            var path = @"C:\tutorials\CSharp-programming-Beginner\Sample\file1.txt";

            string dummyText = @"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
                                tempor incididunt ut labore et dolore magna aliqua.";
            // open a file and append string.
            File.AppendAllLines(path, dummyText.Split(Environment.NewLine.ToCharArray()).ToList<string>());
            // append new text to file
            File.AppendAllText(path, "This is a new Line");
            // overwrite contents with new ones
            File.WriteAllText(path, "text overwritten");
            // read all contents
            var contents = File.ReadAllText(path);
            Console.WriteLine(contents);

            // Check whether file exists/not
            var status = File.Exists(path);
            Console.WriteLine(status);

            // copy file to new director.
            var newPath = @"C:\tutorials\dummyFile.txt";
            File.Copy(path, newPath);
            var content = File.ReadAllText(newPath);
            Console.WriteLine(content); 

            // move file to new location
            var newDummyPath = @"C:\Users\Jissmon\move.txt";
            File.Move(path, newDummyPath);
            Console.WriteLine(File.ReadAllText(newDummyPath));
        }
    }

```

---

