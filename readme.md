# C# AND .NET FRAMEWORK

- C# is a progarmming language

- .NET is a framework for building applications on windows

- CLR(COMMON LANGUAGE RUNTIME)
- job is to translate IL(Intermediate Language) code to machine code at runtime. that process called JIT(Just in Time Compilation)
- thus v can run C# application in another machines. ie. machine independent. but that machine should have CLR.

## our first C# application

### NameSpace and Assembly

- A namespace is a container for related classes.
- So as your application grows in size, you may want to group the related classes into various namespaces for better maintainability.
- As the number of classes and namespaces even grow further, you may want to physically separate related namespaces into separate assemblies.
- An assembly is a file (DLL or EXE) that contains one or more namespaces and classes.
- An EXE file represents a program that can be executed.
- A DLL is a file that includes code that can be re-used across different programs.

## Variables and Constant

- declaring a variable, use _var_
- _var_ is mutable

```C#
var name = "jiss";
var num = 60;
```

- constants r immuatble in C#
- declaring constant

```C#
const float val = 3.14f;
```

## primitive types

![image](./screenshots/Screenshot-1.png 'image')

## demo

```C#
 static void Main(string[] args)
        {

            byte number = 10;
            Console.WriteLine(number);

            int number2 = 30;
            Console.WriteLine(number2);

            float marks = 4.6F;
            Console.WriteLine(marks);

            double percentage = 230.44;
            Console.WriteLine(percentage);

            string name = "Jissmon";
            Console.WriteLine(name);

            bool status = true;
            Console.WriteLine(status);
        }
```

## TypeConversion

```C#
 static void Main(string[] args)
        {
            /* Convert int -> byte */
            int x = 10;
            /* casting int value to byte, since byte range is less than int */
            byte y = (byte) x;
            Console.WriteLine(y + " is a " +y.GetType() + " type");

            /* byte -> int*/
            byte num = 100;
            int num1 = num;
            Console.WriteLine(num1 + " is an " + num1.GetType() + " type") ;

            /* string -> int, Parse() */
            string username = "5670";
            int username2 = int.Parse(username);
            Console.WriteLine(username2 + " is a " + username2.GetType() + " type");

            /* int -> string, ToString() */
            int num3 = 5000;
            string num4 = num3.ToString();
            Console.WriteLine(num4 + " is a " + num4.GetType() + " type");
        }
```

---

## Operators

```C#
 static void Main(string[] args)
        {
            int num1 = 70;
            int num2 = 60;
            int num3 = 100;

            // >, <, &&
            if(num1 > num2 && num3 < num1)
            {
                Console.WriteLine(num1 + "greater");
            }
            else if(num2 > num3)
            {
                Console.WriteLine(num2 + "greater");
            }
            else
            {
                Console.WriteLine(num3 + " greater");
            }

            // equals
            if(num2 == num3)
            {
                Console.WriteLine(num2 + " equals " + num3);
            }

            // not equal
            if(num1 != num3)
            {
                Console.WriteLine(num1 + " not equals " + num3);
            }

            // not operatos
            Console.WriteLine((!(num3 >= 100)));

            // OR operartos
            Console.WriteLine((num1 == num3 || num2 <= num3));
        }

```

---

## Classes

```C#
using System;

namespace Classes
{
    // create a class
    public class FullName
    {
        // define properties
        public string firstName;
        public string lastName;

        // define a method
        public void getName()
        {
            Console.WriteLine("My name is " + firstName + " " + lastName);
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            // instantiation of object of FullName class - assign values to propreties
            var obj1 = new FullName()
            {
                firstName = "Jissmon",
                lastName = "Jose"
            };
            // invoke the method using objcet
            obj1.getName();
        }
    }
}

```

- object creation - invoking object methods- assign properties values are done in Main() method.

- when v have an pplication -it might have diffrent number of classes - we dont out all classes in one file- ibnstead create spearte files .cs file for each such claless.

**Program.cs**

```C#
using Classes.Math;
using System;
using System.Net.Http.Headers;

namespace Classes
{
    class Program
    {
        static void Main(string[] args)
        {
           // instantiation of object of FullName class - assign values to each property
            var obj1 = new FullName()
            {
                firstName = "Jissmon",
                lastName = "Jose"
            };
            // invoke the method using objcet
            obj1.GetName();

            // access Calculator class and associated methods
            var calc = new Calculator();
            var result = calc.Add(40, 50);
            Console.WriteLine(result);
            Console.WriteLine(calc.Divide(40, 3));

        }

    }
}

```

**FullName.cs**

```C#
using System;

namespace Classes
{
    public class FullName
    {
        // define properties
        public string firstName;
        public string lastName;

        // define a method
        public void GetName()
        {
            Console.WriteLine("My name is " + firstName + " " + lastName);
        }
    }
}

```

-- Here this FullName is defined in other class file - but it is instantiated and it's methods are
invoked in Program.cs file.

---

## Arrays in C

**arrayOne.cs**

```C#
 public class ArraysOne
    {
        // initilize an array of numbers
        public int[] numbers ={ 10, 20, 30 };
        // initialize an array of string,
        public string[] names = { "jissmon", "justin", "george" };
	//  intialize a float array
        public float[] decimals = {10.2F, 33.11F, 55.66F};

	public void getNumbers()
        {
            // usinf normal for loop
            for (int i =0; i < numbers.Length; i++ )
            {
                Console.WriteLine(numbers[i]);
            }
        }

        public void getNames()
        {
	    // using foreach
            foreach (string element in names)
            {
                Console.WriteLine($"Name: {element}");
            }
        }

	public void getDecimals()
        {
            foreach(float nums in decimals)
            {
                Console.WriteLine($"Value: {nums}");
            }
        }

    }
```

- Next access the class from Programs.cs file - instantiate an object - call methods.

**Program.cs**

```C#

    class Program
    {
        static void Main(string[] args)
        {
  // access arrayOne class
            var arr1 = new ArraysOne();
            arr1.getNumbers();
            arr1.getNames();
            arr1.getDecimals();

	}
     }
```

# Strings in CSharp

**StringsCls.css**

```C#

namespace Classes.Computers
{
    class StringsCls
    {
        public string firstName = "jissmon";
        public string lastName = "jose";

        public string ConcatenateBoth()
        {
            // call Concat method from string class.
            var fullName = string.Concat(firstName, " ", lastName);
            return fullName;
        }
        public string FormatName()
        {
            // use Format to return value
            var fullName = string.Format("My Name is {0} {1}", firstName, lastName);
            // {0}- firstName
            // {1} - lastName
            return fullName;
        }

        public string JoinNames()
        {
            // inittialze an array of strings
            var names = new string[] { "jissmon", "ajith", "george" };
            // invoke Join() - pass separator as first argument, array names as sec arg.
            return string.Join("-", names);
        }
          public string OrderText()
        {
            // use verbatim string to show text in multiple lines, can use this instead of new line character \n,
            // use, @ special character as verbatim identifier.
            var text = @"hi jisssmon,
            this is called visual studio ide.
            you can do your work coding here.";

            return text;
        }
    }
}

```

**Program.cs**

```C#
    // access StringsCls()
    // invoke Formatnames, joinnames, verbatim  method
    var obj = new StringsCls();
    var concateText = obj.ConcatenateBoth();
    var formattedName = obj.FormatName();
    var joinedName = obj.JoinNames();
    var verbatimText = obj.OrderText();
    Console.WriteLine(concateText);
    Console.WriteLine(formattedName);
    Console.WriteLine(joinedName);
    Console.WriteLine(verbatimText);
```

---

# Enums

- Use enum when v have number of related constants.

- To define an enumeration type, use the enum keyword and specify the names of enum members:

- basic dsefinition:

```C#
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

to access any enum member from enum,

```C#
ErrorCode.None
ErrorCode.Unknown
```

- By default, the associated constant values of enum members are of type _int_. they start with zero and increase by one following the definition text order.

- You cannot define a method inside the definition of an enum. To add, create an extension method.

## Enums Demo

```C#

namespace Enums
{
    // enum type definition
    public enum ShippingMethod{
        // ShippingMethod - ia an enum type
        // define enum members and their constant values
        RegularAirMail = 50,
        RegisterAirMail = 150,
        Express = 300
    }
    class Program
    {
        static void Main(string[] args)
        {
            // access the enum member
            Console.WriteLine(ShippingMethod.RegisterAirMail);

            // to get integer value asscoiate with that memeber , cast enum type to int type.
            var getRegisterAirMail = (int)ShippingMethod.RegisterAirMail;

            Console.WriteLine(getRegisterAirMail);

            // suppose got a value from client, access the enum member associated with that value
            var getValue = 300;
            // so cast this value to ShippingMethod enum type
            var castToEnum = (ShippingMethod)getValue;
            Console.WriteLine(castToEnum);

            // Example
            var getExpress = ShippingMethod.Express;
            var getExpval = (int)getExpress;
            Console.WriteLine(getExpval);

        }
    }
}


```

## Enum to String and Vice-Versa

- enum to string, use ToString()
- string to enum, use Enum.Parse(typeof(Target type), strning value)

### Demo

```C#
  // Enum to String
    var getRegularAirMail = ShippingMethod.RegularAirMail;
    Console.WriteLine(getRegularAirMail.GetType()); // enums.shippingmethod type
    // call ToString()
    var convertedToString = getRegularAirMail.ToString();
    Console.WriteLine(convertedToString.GetType()); // Systrem.string

    //string to enum
    var currValBefore = "Express";
    Console.WriteLine(currValBefore.GetType()); // System.String type
    // use Enum.Parse() - args - ShippingMethod which is the type we want to convert the string to, string value.
    // ShippinhMethod is specified with in typeof operator. Enums.Parse() returns an object, so cast output to ShippingMethod typ
    var currValAfter = (ShippingMethod)Enum.Parse(typeof(ShippingMethod), currValBefore);
    Console.WriteLine(currValAfter.GetType()); // Enums.Shippingmethod
    Console.WriteLine(currValAfter);
```

---

# reference types and value types

```C#
 class ValueAndReferenceTypes
{

    public void ValueTypes()
    {
        var num1 = 50;
        var num2 = num1;
        num2++;
        Console.WriteLine($" num1: {num1 }, num2: {num2}");
        // here a memory locatoin is alloated for num1 ro store value 50,
        // a copy of value 50 assigned to num2 which resides in different memory location.
        // later increment num2.
        // so here change in num2 didnt reflect in num1 since both in diff locations.
        // value typs r stored in stack.
    }

    public void ReferenceTypes()
    {
        var mark1 = new int[] { 40, 33, 44 };
        var mark2 = mark1;
        mark1[0] = 60;

        foreach (
            int a in mark1
            )
        {
            Console.WriteLine($"array1: {a}");
        }

        foreach(int a1 in mark2)
        {
            Console.WriteLine($"array2: {a1}");
        }

        // here v change value of index 0 in mark1 array,
        // that change will happen in mark2 array as well

        // v create an array in heap with an address.
        // v assign that array to a variable called mark1.
        // this variable stored in stack.
        // when v copy mark1 to mark2 variable.
        // mark2 stored in stack with the same address of mark1.
        // here both mark1 and mark points to same array in the heap.
        // thus if change made in either of the mark1 and mark2,
        // it reflects in other one too.
    }
}

```

## Screenshots

### value type

![image](./screenshots/value.png 'image')

### reference type

![image](./screenshots/reference.png 'image')

---

# Collections

## dictionaries

```C#
 class Program
    {
        static void Main(string[] args)
        {
            // intialize a Dictionary Object, use IDictionary<TKey, TValue>
            IDictionary<int, string> dict = new Dictionary<int, string>
            {
                { 10, "ten" },
                { 30, "thirty" },
                { 7, "seven" }
            };

            // accessing dictionary elements, use foreach
            // - use KeyValuePair Type
            foreach (KeyValuePair<int, string> item in dict)
            {
                Console.WriteLine($"Key: {item.Key}, Value: {item.Value}");
            }

            // accesing the individual element using key
            Console.WriteLine(dict[10]);
            Console.WriteLine(dict[30]);
            Console.WriteLine(dict[7]);
        }
    }

```
