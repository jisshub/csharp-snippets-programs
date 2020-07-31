# Strings

```C#
 static void Main(string[] args)
        {

            var fullName = "hugh jackman";

            // Split - gives an array
            var nameSplitted = fullName.Split(' ');
            var firstName = nameSplitted[0];
            var lastName = nameSplitted[1];
            Console.WriteLine($"Firstname: {firstName}, Lastname: ${lastName}");

            // trim - removes all whitespaces
            var nameTrim = fullName.Trim();
            Console.WriteLine($"before trim: {fullName}, afetr trim: {nameTrim}");

            // replace string
            Console.WriteLine(fullName.Replace("jackman", "ackmaan"));

             // check whether string is valid / not,
            // use static method IsNullOrWhiteSpace on String class
            var value2 = "Jissmon";
            if (String.IsNullOrWhiteSpace(value2))
            {
                // value2 is null or just whitespace - invalid
                Console.WriteLine("Invalid");
            }
            else
            {
                // any value is provided- valid
                Console.WriteLine("valid");
            }

            // Example
            var value3 = " ";
            if (String.IsNullOrWhiteSpace(value3))
            {
                Console.WriteLine("Invalid");
            }
            else
            {
                Console.WriteLine("Valid");
            }


        }
```

---

