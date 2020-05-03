# Basics

## .NET Program Execution

1. The .NET application gets compiled into Intermediate language \(IL\). IL is also referred as Common Intermediate language \(CIL\) and Microsoft Intermediate language \(MSIL\). Both .NET and non .NET applications generate an assembly. Assemblies have an extension of .DLL or .EXE. For example if you compile a windows or Console application, you get a .EXE, where as when we compile a web or Class library project we get a .DLL. The difference between a .NET and NON .NET assembly is that, DOTNET Assembly is in intermediate language format where as NON DOTNET assembly is in native code format.
2. NON DOTNET applications can run directly on top of the operating system, where as DOTNET applications run on top of a virtual environment called as Common Language Runtime \(CLR\). CLR contains a component called Just In-Time Compiler \(JIT\), which will convert the Intermediate language into native code which the underlying operating system can understand.

So, in .NET the application execution consists of 2 steps 1. Language compiler, compiles the Source Code into Intermediate Language \(IL\) 2. JIT compiler in CLR converts, the IL into native code which can then be run on the underlying operating system.

![](../.gitbook/assets/image%20%2825%29.png)

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

## const V.S. readonly

 The `readonly` keyword is used to declare a member variable a constant, but allows the value to be calculated at runtime. This differs from a constant declared with the `const` modifier, which must have its value set at compile time

| READONLY KEYWORD | CONST KEYWORD |
| :--- | :--- |
| In C\#, readonly fields can be created using readonly keyword | In C\#, constant fields are created using const keyword. |
| ReadOnly is a runtime constant. | Const is a compile time constant. |
| The value of readonly field can be changed. | The value of the const field can not be changed. |
| It cannot be declared inside the method. | It can be declared inside the method. |
| In readonly fields, we can assign values in declaration and in the contructor part. | In const fields, we can only assign values in declaration part. |
| It can be used with static modifiers. | It cannot be used with static modifiers. |



