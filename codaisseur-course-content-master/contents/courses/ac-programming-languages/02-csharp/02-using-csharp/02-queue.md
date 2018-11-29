---
title: Queue
description: Create singly linked list and a double linked list data structure
tags:
  - Data structures
---

# Stack

> From [Wikipedia](https://en.wikipedia.org/wiki/Queue_(abstract_data_type)):
> 
>In computer science, a queue is a particular kind of abstract data type (ADT) or collection in which the entities in the collection are kept in order and the principal (or only) operations on the collection are the addition of entities to the rear terminal position, known as enqueue, and removal of entities from the front terminal position, known as dequeue. This makes the queue a First-In-First-Out (**FIFO**) data structure. In a FIFO data structure, the first element added to the queue will be the first one to be removed. 

![queue](https://upload.wikimedia.org/wikipedia/commons/thumb/5/52/Data_Queue.svg/405px-Data_Queue.svg.png "Queue")


# Assignment

Write a your own (fixed capacity) Queue data structure (a class) that uses an Array as the underlying data structure to store the data. This Queue should be able to store integers. Your queue class should have the following methods:
- `void Enqueue(int value)` 
- `int Dequeue()`
- `bool IsEmpty()`
- `bool IsFull()`

Write a C# console application that initializes that takes input from the user, numbers, puts them on the stack. When the user types `r` it will dequeue all items of the queue and displays them, each item on a new line. `q` will exit the program.

*Tip: Use a Unit test project to test your non user interaction code, this is probably faster than running the console application each time you made a change. see: [unit testing with nunit](https://docs.microsoft.com/en-us/dotnet/core/testing/unit-testing-with-nunit)*

*Tip: you need to keep track of the head and the tail of the queue in a class variables. It could help to visualize it on paper first*

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

### Next steps

#### Study material
- Please watch [Linked lists](https://www.youtube.com/watch?v=_jQhALI4ujg)
- Please read up until page 6 of [Linked list basics](http://cslibrary.stanford.edu/103/LinkedListBasics.pdf)

#### Assignment
- Now modify your Queue class such that it uses a Linked List instead of an array as the underlying data structure. Your Console application (and tests) should still work. You can create a new class `LinkedListInt` and use unit tests to test it's functionality.

## Try to answer the following questions
- What are the advantages and disadvantages of using an Array, and of a Linked List as the underlying data structure?
- What applications could the Queue have in software?
- When wouldn't you use a Queue to store data?
- What are the performance characteristics compared to an Array, when searching or inserting?