---
title: Installation
description: |
  Installing a C# compiler, runtime and editor
---

# Installing a C#

C# is a compiled language. That means we need a program to convert our source code to an executable or library in binary format that contains instructions for your CPU. C# is compiled to [Common Intermediate Language]https://en.wikipedia.org/wiki/Common_Intermediate_Language) (CIL) that can run on a .NET Runtime. The runtime is a tiny virtual machine that executes the CIL and translates it to native instructions. 

**Think about the advantages and disadvantages of this architecture.**

## To install C#

There are many (free) editors that support C#. 

If you are on a Windows or Mac OS I would highly recommend Visual Studio, it has the best tooling and integrated support and it has a fee version.

Whatever platform you are on, make sure you have installed the 
- First install the .NET Core SDK [https://www.microsoft.com/net/download](https://www.microsoft.com/net/download) for your OS.

### Visual Studio
- [Visual Studio (Community Edition) for Mac](https://visualstudio.microsoft.com/vs/mac/)
- [Visual Studio 2017 (Community Edition) for Windows](https://visualstudio.microsoft.com/)

### Visual studio code
Visual studio code has some great extensions to work with C#.
- First install the .NET Core SDK [https://www.microsoft.com/net/download](https://www.microsoft.com/net/download) for your OS.
- Install the C# Extension(s) see [*Installing C# Support*](https://code.visualstudio.com/docs/languages/csharp#_installing-c35-support) section.
- Optionally follow the [Video Tutorial on Getting Started with C# in VS Code with .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-Csharp-NET-Core-Windows)

### Others
- [MonoDevelop](https://www.monodevelop.com/download/#fndtn-download-lin) is a multiplatform C# (and .NET) IDE
- [Rider: The Cross-platform .NET IDE from JetBrains](https://www.jetbrains.com/rider/)

## Check installation

Follow the [.NET Tutorial - Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial) to create your first console application.