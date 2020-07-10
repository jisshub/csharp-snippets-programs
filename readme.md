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

## Arrays in C#

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




