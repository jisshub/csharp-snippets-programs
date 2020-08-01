# Path Class

```C#

static void Main(string[] args)
        {
            var path = @"C:\tutorials\mongodb\authors.json";

            // get Extension - sue GetExtension()
            var extension = Path.GetExtension(path);
            Console.WriteLine($"Extension is {extension}");

            // filename- use GetFileName()
            var fileName = Path.GetFileName(path);
            Console.WriteLine($"Filename is " + fileName);

            // get directory name 
            var dirName = Path.GetDirectoryName(path);
            Console.WriteLine("Directory Name is " + dirName);

            // filename wwoth no extension 
            var fileNameNoExt = Path.GetFileNameWithoutExtension(path);
            Console.WriteLine("FileName wth no extension " + fileNameNoExt);
        }

```

