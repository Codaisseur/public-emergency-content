---
title: Stack
description: Create singly linked list and a double linked list data structure
tags:
  - Data structures
---

# Stack

> From [Wikipedia](https://en.wikipedia.org/wiki/Stack_(abstract_data_type)):
>
> In computer science, a stack is an abstract data type that serves as a collection of elements, with two principal operations:
>
> - **push**, which adds an element to the collection, and
> - **pop**, which removes the most recently added element that was not yet removed.
>
> The order in which elements come off a stack gives rise to its alternative name, **LIFO** (last in, first out). Additionally, a peek operation may give access to the top without modifying the stack. The name "stack" for this type of structure comes from the analogy to a set of physical items stacked on top of each other, which makes it easy to take an item off the top of the stack, while getting to an item deeper in the stack may require taking off multiple other items first.

![stack](https://upload.wikimedia.org/wikipedia/commons/thumb/2/29/Data_stack.svg/391px-Data_stack.svg.png "stack")

## Study material
- Please watch [Reverse Polish Notation and The Stack](https://www.youtube.com/watch?v=7ha78yWRDlE)

# Assignment

Write a your own Stack data structure (a class). This Stack should be able to only store integers. 

Write a C# console application that initializes that takes input from the user, numbers, puts them on the stack. When the user types `r` it will pop all items of the stack and displays them, each item on a new line. `q` will exit the program.

*Tip: Use a Unit test project to test your non user interaction code, this is probably faster than running the console application each time you made a change. see: [unit testing with nunit](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-nunit)*

Example boilerplate:
```csharp
static void Main()
{
    //Print initial messages when the program stars
    Console.WriteLine("Welcome to the program.");
    Console.WriteLine("Please input some numbers followed by <enter>. When you are done, press r to print the data structure, or input q to quit.");

    while (true)
    {
        //Read inputs from the command line
        //Waits until a line is being read from the console
        string inputFromConsole = Console.ReadLine();

        if (inputFromConsole == "r")
        {
            //Print 
            Console.WriteLine("Print");
            //Reset 
        }

        if (inputFromConsole == "q")
        {                 
            Console.WriteLine("Exiting... Bye!!");
            return;
        }

        //If the input can be parsed as an Integer
        if (int.TryParse(inputFromConsole, out int inputNumber))
        {
            //Add inputNumber to the data structure
            Console.WriteLine($"Added {inputNumber}.");
        }
    }
}
```

### Done?
- Now modify your Stack class such that is can contain any Type. Use Generics to achieve this. Your Console application should still work with integers. You should only have to change the initialization. 
```CSharp
MyStack<int> stack = new MyStack<int>();
```

## Try to answer the following questions
- If all the instructions of your program are items on a stack data structure, can you try to explain what a stacktrace would be?
- How does this data structure relate to a Stack or a Doubly Linked list?

## Want more?
If you want to experiment more with this data structure try to create a tower of hanoi game with 3 stacks.

### Further reading
- [https://en.wikibooks.org/wiki/Data_Structures/Stacks_and_Queues](https://en.wikibooks.org/wiki/Data_Structures/Stacks_and_Queues)
- [https://www.cs.cmu.edu/~adamchik/15-121/lectures/Stacks%20and%20Queues/Stacks%20and%20Queues.html](https://www.cs.cmu.edu/~adamchik/15-121/lectures/Stacks%20and%20Queues/Stacks%20and%20Queues.html)