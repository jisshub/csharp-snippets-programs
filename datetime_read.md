# DateTime Struct

- C# includes DatTime struct to work with dates and times.

```C#

static void Main(string[] args)
        {
            // create a datetime object.
            var dateTime = new DateTime(2020, 7, 28);
            Console.WriteLine(dateTime);

            // get current date and time
            Console.WriteLine(DateTime.Now);
            // get today's date and time
            Console.WriteLine(DateTime.Today);

            // aslo explicity get the hour, minute, day, date
            Console.WriteLine(DateTime.Now.Year);
            Console.WriteLine(DateTime.Now.Hour);
            Console.WriteLine(DateTime.Now.Date);
            Console.WriteLine(DateTime.Now.Day);

            // add days, hour, years
            Console.WriteLine(DateTime.Now.AddDays(4));
            Console.WriteLine(DateTime.Now.AddYears(2));
            Console.WriteLine(DateTime.Now.AddHours(3));

            // DateTime -> String, use ToString()
            var now = DateTime.Now;

            // default format
            var stringDate = now.ToString();
            Console.WriteLine($"{stringDate.GetType()}, {stringDate}");

            // mm/dd/yyyy format
            var string2 = now.ToString("MM/dd/yyyy");
            Console.WriteLine($"{string2.GetType()}, {string2}");

            // yyyy/dd/MM format
            var string3 = now.ToString("yyyy/MM/dd");
            Console.WriteLine($"{string3.GetType()}, {string3}");

            // String -> DateTime object, use TryParse() method
            var currDateStr = "10/12/2020";
            // parse string to DateTime object
            DateTime.TryParse(currDateStr, out DateTime dt); // returns boolean
            // to get datetime value use dt.
            Console.WriteLine($"Date: {dt}, Type: {dt.GetType()}");


            // Strit -> DateTime object Example
            var d = "16/11/2020";
            DateTime.TryParse(d, out DateTime dateObj);
            Console.WriteLine($"{dateObj}, {dateObj.GetType()})";
        }
```
