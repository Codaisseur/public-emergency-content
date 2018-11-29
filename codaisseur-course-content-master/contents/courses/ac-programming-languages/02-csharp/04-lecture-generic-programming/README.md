---
title: Generics
description: What are generics and type parameters, and why is it useful?
---
https://en.wikipedia.org/wiki/Generic_programming
# Generics

This lecture will cover topics about generics.

## Generic programming
Generic Programming is a style of programming where algorithms and other programming bits use unspecified data and class types. This means that one could write a function such as `Divide<T>(T a, T b)` and later pass on an integer as a and b, or a long integer, or any other type of variable. This is most useful in strongly-typed languages, as weakly-typed languages have no need for them.

>The term generic programming was originally coined by David Musser and Alexander Stepanov in a more specific sense than the above, to describe a programming paradigm whereby fundamental requirements on types are abstracted from across concrete examples of algorithms and data structures and formalized as concepts, with generic functions implemented in terms of these concepts, typically using language genericity mechanisms as described above.

## Generics explanation and examples in C#
Different languages implement generics in different ways, we will focus on C# only.
Generics are useful in a strong-typed language, since it has type checking and be strict on the types you pass to a method.

First let's look at a collection type without generics. Say I want to implement a List, a dynamic data structure that can store items without generics. In most OO languages every type (class) inherits from the class Object. So if we wanted to make a List that could store anything we could do it like this:
``` Csharp
public class List
{
    public int AddItem(Object item)
    {
        //store it internally return the index
        Count++;
    }

    public Object GetItem(int index)
    {
        //lookup value
        return value;
    }
    //RemoveItem(Object item) ...
    public int Count{};//return number of items
}

//Now we need a List that can contain strings, well a string is an Object so we can use this List

List myListOfStrings = new List();

int doctorIndex = myListOfStrings.Add("The Doctor");
int claraIndex  = myListOfStrings.Add("Clara");

//Now I want to get my strings back from the List

string doctorString = myListOfString.GetItem(doctorIndex);//ERROR!!
//the above line will give a compile error (Remember Inheritance. A string is an object, but an object is not a string)

//To fix this, can cast the object to a string, since we are sure we put a string in there, right?
string doctorString = (string) myListOfString.GetItem(doctorIndex); // this compiles

//but what happens now, if I accidentally put something that is not a string in the list, and try to cast that?
List anotherList = new List();
int index = anotherList.Add(123329837);//That's right, we put a number in there, not a string
string myString = (string) anotherList.GetItem(index);//This compiles.

//When we run the program, we will get a Runtime error!, because an int is not a string. So our compiler couldn't catch the error.

//The solution before generics: Create a Custom List for each Type you want to use like:

public class StringList
{
    public int AddItem(string item)
    {
        //store it internally return the index
        Count++;
    }

    public string GetItem(int index)
    {
        //lookup value
        return value;
    }
    //RemoveItem(Object item) ...
    public int Count{};//return number of items
}
//This works great, and you are strongly typed, the compiler catches errors and it is clear to developers what kind of list it is.
//But it is tedious work, the data structure is basically the same for every type. So could we pass a Type (Class) as a sort of parameter and Generalize?

//With generics you can. Let's create a generic List

public class GenericList<T> //Notice the <T>?, that means we have a Type parameter, you can use any letter or word, the T is just a variable.
{
    //This now uses the Type variable T
    public int AddItem(T item)
    {
        //store it internally return the index
        Count++;
    }

    //This now returns an object of type T
    public T GetItem(int index)
    {
        //lookup value
        return value;
    }
    //RemoveItem(Object item) ...
    public int Count{};//return number of items
}

//Now we can create a list of any type, we just need to pass the Type we want in the type variable.
GenericList<string> myGenericStringList = new GenericList<string>();
//myGenericStringList now only accepts and returns strings, since T is a string type

//if we want to pass it another type the compiler will give an error
myGenericStringList.Add(12049795687);//Error!!

//And we can do this for any type
GenericList<int> myGenericIntList = new GenericList<int>();

//You can also use generic parameters in methods, you can even use multiple type parameters

//<TA, TB> says: I have 2 type parameters, the first one is called TA, and the second one is called TB.
public static Tuple<TA,TB> CreateTuple<TFrom, TB>(TA item1, TB item2)
{
    return new Tuple<TA, TB>(item1, item2)
}

public class Tuple<TOne, TWo>
{
    public readonly TOne Item1;
    public readonly TWo Item2;

    public Tuple(TOne item1, TWo item2)
    {
        Item1 = item1;
        Item2 = item2;
    }
}

```


For more background see also: 
- [https://en.wikipedia.org/wiki/Generic_programming](https://en.wikipedia.org/wiki/Generic_programming)
- [https://en.wikibooks.org/wiki/C_Sharp_Programming/Generics](https://en.wikibooks.org/wiki/C_Sharp_Programming/Generics)