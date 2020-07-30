# StringBuilder

- defined in System.Text

- a mutable string

- easy and fast to create and manipulate strings.

- Use StringBuilder when you need to append more than three or four strings.

- but gives string manipulation methods.
    1. Append
    2. Insert
    3. Remove
    4. Replace
    5. Clear 

## StringBuilder Demo

```C#

static void Main(string[] args)
        {
            // create a StringBuilder object
            StringBuilder s1 = new StringBuilder("Hello World");
            Console.WriteLine(s1.GetType()); // it is not string type

            // ToString(), convert to string
            var ConvStr = s1.ToString();
            Console.WriteLine($"{ConvStr} is {ConvStr.GetType()} type");

            // append to StringBuilder
            StringBuilder s2 = new StringBuilder();
            s2.Append("Jissmon");
            s2.AppendLine(); // appends new line
            s2.Append("Ajith");
            Console.WriteLine(s2);

            // Replace() - replace old char with new one.
            StringBuilder s3 = new StringBuilder("Thala Ajith");
            s3.Replace("Ajith", "Jissmon");
            Console.WriteLine(s3);
        }

```

![String Builder](https://www.tutorialsteacher.com/csharp/csharp-stringbuilder)

---
