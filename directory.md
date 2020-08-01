# Direcoty class

- methods are direclty invoked on Directory class.

- always use *System.IO* namespace

```C#
static void Main(string[] args)
        {

            // Create a Directory, use CreateDirectory

            Directory.CreateDirectory(@"C:\tutorials\CSharp-Programming-Beginner\Sample\testdir");

            // get all files in a directory, use GetFiles() - returns a string[]
            var files= Directory.GetFiles(@"C:\tutorials\html_css\modern-html-and-css");
            foreach(var file in files)
            {
                Console.WriteLine(file);
            }

            // get all directories, use GetDirectories()
            var directories = Directory.GetDirectories(@"C:\tutorials\html_css\modern-html-and-css");
            foreach(var dir in directories)
            {
                Console.WriteLine(dir);
            }

            // check direcotories exists, use Exists() method
            if (Directory.Exists(@"C:\tutorials\html_css\modern-html-and-css"))
            {
                Console.WriteLine("exists");
            }
        }
```

