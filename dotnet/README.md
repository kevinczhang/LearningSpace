# Basics

## .NET Program Execution

1. The .NET application gets compiled into Intermediate language \(IL\). IL is also referred as Common Intermediate language \(CIL\) and Microsoft Intermediate language \(MSIL\). Both .NET and non .NET applications generate an assembly. Assemblies have an extension of .DLL or .EXE. For example if you compile a windows or Console application, you get a .EXE, where as when we compile a web or Class library project we get a .DLL. The difference between a .NET and NON .NET assembly is that, DOTNET Assembly is in intermediate language format where as NON DOTNET assembly is in native code format.
2. NON DOTNET applications can run directly on top of the operating system, where as DOTNET applications run on top of a virtual environment called as Common Language Runtime \(CLR\). CLR contains a component called Just In-Time Compiler \(JIT\), which will convert the Intermediate language into native code which the underlying operating system can understand.

So, in .NET the application execution consists of 2 steps 1. Language compiler, compiles the Source Code into Intermediate Language \(IL\) 2. JIT compiler in CLR converts, the IL into native code which can then be run on the underlying operating system.

![](../.gitbook/assets/image%20%2819%29.png)

## Managed vs Unmanaged Code

### Managed Code

“The code, which is developed in .NET framework is known as managed code. This code is directly executed by CLR with the help of managed code execution. Any language that is written in .NET Framework is managed code”.

### Unmanaged Code

The code, which is developed outside .NET framework is known as unmanaged code.

“Applications that do not run under the control of the CLR are said to be unmanaged, and certain languages such as C++ can be used to write such applications, which, for example, access low - level functions of the operating system. Background compatibility with the code of VB, ASP and COM are examples of unmanaged code”.

Unmanaged code can be unmanaged source code and unmanaged compile code. Unmanaged code is executed with the help of wrapper classes.

Wrapper classes are of two types: 

* CCW \(COM Callable Wrapper\).
* RCW \(Runtime Callable Wrapper\).

## Interface V.S. Abstract Class

Theoretically their are some differences between Abstract Class and Interface which are listed below:

* A class can implement any number of interfaces but a subclass can at most use only one abstract class. 
* An abstract class can have non-abstract methods \(concrete methods\) while in case of interface all the methods has to be abstract. 
* An abstract class can declare or use any variables while an interface is not allowed to do so. 
* In an abstract class all data member or functions are private by default while in interface all are public, we can’t change them manually. 
* In an abstract class we need to use abstract keyword to declare abstract methods while in an interface we don’t need to use that. 
* An abstract class can’t be used for multiple inheritance while interface can be used as multiple inheritance. 
* An abstract class use constructor while in an interface we don’t have any type of constructor.

## constant V.S. read only in c\#

Constant \(const\) and Readonly \(readonly\) both looks like same as per the uses but they have some differences:

Constant is known as “const” keyword in C\# which is also known immutable values which are known at compile time and do not change their values at run time like in any function or constructor for the life of application till the application is running.

Readonly is known as “readonly” keyword in C\# which is also known immutable values and are known at compile and run time and do not change their values at run time like in any function for the life of application till the application is running. You can assay their value by constructor when we call constructor with “new” keyword.

