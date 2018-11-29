---
title: Object oriented programming
description: What is Object Oriented programming what is it's use? How does this relate to procedural and imperative programming.
---

#Background: Imperative and procedural programming

## Imperative programming
An imperative programming language uses a sequence of statement to modify the state of the program. Each one is executed in turn (one could say sequential programming.) Basic and, C are common examples. But almost every non-declarative (and functional languages are mostly declarative languages) language can be used imperatively. A lot of SQL, like the SELECT statement can be considered declarative.
This look very much like the way your cpu would operate, sequentially, instruction by instruction.

See also: [https://en.wikipedia.org/wiki/Imperative_programming](https://en.wikipedia.org/wiki/Imperative_programming)

## Procedural programming
Procedural programming is a way to structure your programs in a procedures (functions). You could say procedural programming you van apply to imperative languages. It has it's foundation in Structured Programming which has scientific foundations, in that programs must be written with provability in mind.

>From [wikibooks](https://en.wikibooks.org/wiki/C%2B%2B_Programming/Programming_Languages/Paradigms):
>
>**Procedural** programming can be defined as a subtype of imperative programming as a programming paradigm based upon the concept of procedure calls, in which *statements* are structured into procedures (also known as subroutines or functions). Procedure calls are modular and are bound by scope. A procedural program is composed of one or more modules. Each module is composed of one or more subprograms. Modules may consist of procedures, functions, subroutines or methods, depending on the programming language. Procedural programs may possibly have multiple levels or scopes, with subprograms defined inside other subprograms. Each scope can contain names which cannot be seen in outer scopes.
>
> Procedural programming offers many benefits over simple sequential programming since procedural code:
>
>- is easier to read and more maintainable
>- is more flexible
>- facilitates the practice of good program design
>- allows modules to be used again in the form of code libraries.

For more background see also: [https://en.wikipedia.org/wiki/Structured_programming](https://en.wikipedia.org/wiki/Structured_programming)

# Object Oriented programming

Object oriented programming is an other way to structure imperative programming (and procedural programming) with new constructs and behavior.

A way to encapsulate (hide and structure) data, keep data and behavior in one unit (object) and not be dependant on one global state or shared data structure. To interact via messaging (method calls).
To reuse and classify, similar data and behavior which resulted in what is called polymorphism.

With the origins of Object orientation the were 3 abstract properties defined

- structurally
    - capability of representing arbitrarily structured complex objects
- operationally
    - the ability to operate on complex objects through generic operators
- behaviorally
    - the specification of types and operations (data abstraction)

## Objects -Language characteristics
To be characterized as object-oriented, a language must minimally support an object creation facility and a message-passing facility (message-passing in the sense of method invocation). In addition, many languages provide a mechanism to define classes together with some form of inheritance.
So:
- object creation facility
- message-passing capability
- class capability
- inheritance features

>From [cs.vu.nl](https://www.cs.vu.nl/~eliens/oop/5.html):
>
>Since the introduction of Smalltalk, the predominant notion of objects has been based on the distinction between classes and objects. Classes serve to describe the functionality and behavior of objects, while objects are instance of classes. In other words, classes serve as templates to create objects. Inheritance, then, may be regarded as a means by which to share (descriptions of) object behavior. It is generally defined on classes in terms of a derivation mechanism, that allows one to declare a class to be a subclass of another (super) class. The distinction between classes and objects leads to a number of difficulties, both of a pragmatic and theoretical nature.

> [Alan Kay (creator of Smalltalk)](http://userpage.fu-berlin.de/~ram/pub/pub_jf47ht81Ht/doc_kay_oop_en)
>
>"OOP to me means only messaging, local retention and protection and hiding of state-process, and extreme LateBinding of all things."

## Alternative definition for SmallTalk

1. EverythingIsAnObject.
2. Objects communicate by sending and receiving messages (in terms of objects).
3. Objects have their own memory (in terms of objects).
4. Every object is an instance of a class (which must be an object).
5. The class holds the shared behavior for its instances (in the form of objects in a program list)
6. To eval a program list, control is passed to the first object and the remainder is treated as its message.

### More specified definition by Alan Kay
1. EverythingIsAnObject.
2. Communication is performed by objects communicating with each other, requesting that objects perform actions. Objects communicate by sending and receiving messages. A message is a request for action, bundled with whatever objects may be necessary to complete the task.
3. Objects have their own memory, which consists of other objects.
4. Every object is an instance of a class. A class simply represents a grouping of similar objects, such as integers or lists.
5. The class is the repository for behavior associated with an object. That is, all objects that are instances of the same class can perform the same actions.
So far, similar to 1-5 above. Rule 6 is different. The reference to lists is removed, instead we have:
6. Classes are organized into a singly-rooted tree structure, called the inheritance hierarchy. Memory and behavior associated with instances of a class are available to any class associated with a descendent in this tree structure.

See [http://wiki.c2.com/?AlanKaysDefinitionOfObjectOriented](http://wiki.c2.com/?AlanKaysDefinitionOfObjectOriented) for further reading.

## Classes and Objects

So a Class is a template (blueprint) for an Object. An object is an instance of a class (each instance has it's own memory).
```Csharp
public class Player
{
    //Encapsulation of data, we restrict access and define that _name is data that will belong to the instance of this class and cannot be accessed directly by the 'outside' environment.
    private string _name;
    public string GetName(){ return _name;}
    public Player(string name)
    {
        _name = name;
    }
}

//doctorWho is a variable of the Type Player that is an instance of the Class Player. doctorWho is the object and Player is the class.
Player doctorWho = new Player("Doctor Who");

//amyPond is another object of the type Player. It has its own memory location and contains its own data.
Player amyPond = new Player("Amy Pond");

//All objects of Type Player have the same actions that can be performed on it
public void PerformActionOnPlayer(Player playerObject)
{
    Console.WriteLine(playerObject.GetName());
}

//so we can pass any object of the type player to the method PerformActionOnPlayer
PerformActionOnPlayer(doctorWho);
PerformActionOnPlayer(amyPone);


//Now we define a new Class Extended player that inherits from the class Player by defining `: Player`. The Class (blueprint)  Extended player now has all the data and behavior defined in player and could be extended with more.
public class ExtendedPlayer : Player{
    
    private string _location;

    public ExtendedPlayer(string name) : base(name){}

    public void Travel(string toLocation)
    {
        //for now we just set the toLocation, but image doing some travel logic.        
        _location = toLocation;
    }

    public string GetCurrentLocation()
    {
        return _location;
    }
}

//Now the ExtendedPlayer is a SubType of Player
//That means each ExtendedPlayer is a Player, but not each Player is an ExtendedPlayer

//We can still call PerformActionOnPlayer on an ExtendedPlayer
ExtendedPlayer theNewDoctor = new ExtendedPlayer("Doctor 9");
PerformActionOnPlayer(theNewDoctor);//this will work!!

//we cal call Travel on an extended player
theNewDoctor.Travel("Tardis");

public void PrintLocationForExtendedPlayer(ExtendedPlayer player)
{
    Console.WriteLine(player.GetCurrentLocation());
}

//We can call PrintLocationForExtendedPlayer on an ExtendedPlayer
PrintLocationForExtendedPlayer(theNewDoctor);

//But not on a Player. This wil give a compiler error. A Player is not an ExtendedPlayer, it is more specialized.

PrintLocationForExtendedPlayer(doctorWho);//error!!

```