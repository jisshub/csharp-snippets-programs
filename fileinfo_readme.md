## FileInfo class

```C#
static void Main(string[] args)
        {
            // FileInfo executes on instance.

            // create a fileinfo object
            FileInfo f1 = new FileInfo(@"C:\tutorials\CSharp-Programming-Beginner\Sample\file4.txt");
            Console.WriteLine(f1);

            // create a new file


            // CopyTo
            var destName = @"C:\tutorials\CSharp-Programming-Beginner\file3.txt"
            f1.CopyTo(destName);

            // Exists
            if (f1.Exists)
            {
                Console.WriteLine($"{f1} exsits");
            }
        }

```

more on : ![FileInfo](https://docs.microsoft.com/en-us/dotnet/api/system.io.fileinfo.create?view=netcore-3.1)

---