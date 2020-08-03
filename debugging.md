# Debugging the application

## Using Breakpoint

- Put one or more break points in application and run the application in debug mode.

- When v run the application in the debug mode execution stops at these breakpoints.

- there v can inspect that particular line of code, variable to ensure everthing is ok.

- to put a breakpoint, press *f9*

- run app in debug mode, press *f5*

- sotp the debug mode, press *shift + f5*

- normal run *ctrl + f5*

- We can continue executing the following lines of code by pressing *f10*; also known as **step over method**

- To step into a line of code, v press *f11* - called **step into method**

## Using watch window

- Used while debugging applications.

- Debug > Windows > Watch 1;

- We can add items to be watched while debugging such as variables that are mutable.

**screenshot**

![image](./screenshots/debugwatch.png 'image')

---

## exceptions

### ArgumentOutofRange Exception

```C#
throw new ArgumentOutOfRangeException("code", "count lesser than total items or may be zero or lesser");

```

### ArgumentNullExecption

```C#
  if (list == null)
    {
        throw new ArgumentNullException("argument is null");
    }
```
---

## Call Stack Window

to open,

- first set a breakpoint - run application in debug mode(f5)
    > Debug > Windows > Call Stack window

- used to view order in which the nethods are excuted unitil it reaches the breakpoint.

![image](./screenshots/callstack.png 'image')

- here, *Line 11*  where executed first
- *Line 31* next to be fired
- *Line 44* is the current execution where v specified th breakpoint.

---
