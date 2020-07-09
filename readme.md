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

![image](.\screenshots\Screenshot-1.png 'image')


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





