---
title: Linked lists
description: Create singly linked list and a double linked list data structure
tags:
  - Data structures
---

# Linked lists

## Arrays vs linked lists
Arrays are a great way to store data, but one of the disadvantages is that it is a *static* data structure, it has a fixed size and cannot be resized easily. Or for that matter it is hard to just add an element to the end (or beginning) of the array. 
Many languages and frameworks have dynamic collection types, but they are an abstraction over more dynamic data structures, like maps, trees, linked lists. And some even use arrays under the hood.

A linked list is a called a data structure where each element is a separate object and has a reference to the next element. Element are commonly called nodes.

## Study material
- Please watch [Array vs Linked Lists](https://www.youtube.com/watch?v=DyG9S9nAlUM)
- Please watch [Linked lists](https://www.youtube.com/watch?v=_jQhALI4ujg)
- Please read up until page 6 of [Linked list basics](http://cslibrary.stanford.edu/103/LinkedListBasics.pdf)


# Assignment

Write a C program that initializes a doubly linked list (a linked list that has a reference to the next AND previous element), of 100 elements where each node contains an integer value between 0 and 99, randomly initialized.
The program must get 2 numbers as input from the console and add the first number at the beginning of the list and the second number of the end of the list.
Print the modified linked list to the console such that is looks like this:
`Head[value]<->Node[value]<->Node[value]<->Node[value]... <->Tail[value]`

## Random function
You can use the `rand() % 99;` function to generate pseudo-random numbers.

## Read inputs
You can use the `gets` function to read a line from the console. You can use the `atoi` function to convert a string to an integer. Make sure you include the `stdlib.h` for atoi and `stdio.h` for the `gets` and `printf` functions.

Example:
```c
#include <stdio.h>
#include <stdlib.h>
int main() {
  
  char input[100];
  int inputAsInt;
  
  printf("Please enter a value:\n");
  
  gets(input);//get input from the console
  
  printf("output\n");
  inputAsInt = atoi(input);
  printf("%d",inputAsInt);
  
  return 0;
}
```

## Try to answer the following questions
- What is a dynamic data structure vs. a static data structure?
- What are the disadvantages of a linked list?
- What is a pointer?

## Want more?
If you want to experiment more with this data structure create a sorting algorithm that sorts the list.