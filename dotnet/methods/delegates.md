---
description: >-
  A delegate is a type that represents references to methods with a particular
  parameter list and return type.
---

# Delegates

When you instantiate a delegate, you can associate its instance with any method with a compatible signature and return type. You can invoke \(or call\) the method through the delegate instance. Delegates are used to pass methods as arguments to other methods.

There are three steps involved while working with delegates:

1. Declare a delegate
2. Set a target method
3. Invoke a delegate

 A delegate can be declared using the `delegate` [keyword](https://www.tutorialsteacher.com/csharp/csharp-keywords) followed by a function signature, as shown below.

```text
[access modifier] delegate [return type] [delegate name]([parameters])
```

```csharp
public delegate void MyDelegate(string msg); // declare a delegate

// set target method
MyDelegate del = new MyDelegate(MethodA);
// or 
MyDelegate del = MethodA; 
// or set lambda expression 
MyDelegate del = (string msg) =>  Console.WriteLine(msg);

// target method
static void MethodA(string message)
{
    Console.WriteLine(message);
}
```

## Multicast Delegate

The delegate can point to multiple methods. A delegate that points multiple methods is called a multicast delegate. The "+" or "+=" operator adds a function to the invocation list, and the "-" and "-=" operator removes it.

If a delegate returns a value, then the last assigned target method's value will be return when a multicast delegate called.

```csharp
public delegate int MyDelegate(); //declaring a delegate

class Program
{
    static void Main(string[] args)
    {
        MyDelegate del1 = ClassA.MethodA;
        MyDelegate del2 = ClassB.MethodB;

        MyDelegate del = del1 + del2; 
        Console.WriteLine(del());// returns 200
    }
}

class ClassA
{
    static int MethodA()
    {
        return 100;
    }
}

class ClassB
{
    static int MethodB()
    {
        return 200;
    }
}
```

## Generic Delegate

```csharp
public delegate T add<T>(T param1, T param2); // generic delegate

class Program
{
    static void Main(string[] args)
    {
        add<int> sum = Sum;
        Console.WriteLine(sum(10, 20));

        add<string> con = Concat;
        Console.WriteLine(conct("Hello ","World!!"));
    }

    public static int Sum(int val1, int val2)
    {
        return val1 + val2;
    }

    public static string Concat(string str1, string str2)
    {
        return str1 + str2;
    }
}
```

{% hint style="info" %}
Points to Remember

1. Delegate is the reference type data type that defines the signature.
2. Delegate type variable can refer to any method with the same signature as the delegate.
3. Syntax: \[access modifier\] delegate \[return type\] \[delegate name\]\(\[parameters\]\)
4. A target method's signature must match with delegate signature.
5. Delegates can be invoke like a normal function or Invoke\(\) method.
6. Multiple methods can be assigned to the delegate using "+" or "+=" operator and removed using "-" or "-=" operator. It is called multicast delegate.
7. If a multicast delegate returns a value then it returns the value from the last assigned target method.
8. Delegate is used to declare an event and anonymous methods in C\#.
{% endhint %}

## `Func` Delegate

Func is a generic delegate included in the `System` namespace. It has zero or more input parameters and one out parameter. The last parameter is considered as an out parameter.

![](../../.gitbook/assets/image%20%281%29.png)

```csharp
class Program
{
    static int Sum(int x, int y)
    {
        return x + y;
    }

    static void Main(string[] args)
    {
        Func<int,int, int> add = Sum;

        int result = add(10, 10);

        Console.WriteLine(result); 
    }
}
```

## Action Delegate

 An Action type delegate is the same as [Func delegate](https://www.tutorialsteacher.com/csharp/csharp-func-delegate) except that the Action delegate doesn't return a value. In other words, an Action delegate can be used with a method that has a void return type.

```csharp
static void ConsolePrint(int i)
{
    Console.WriteLine(i);
}

static void Main(string[] args)
{
    Action<int> printActionDel = ConsolePrint;
    printActionDel(10);
}
```

## Predicate Delegate

It represents a method that contains a set of criteria and checks whether the passed parameter meets those criteria or not. A predicate delegate methods must take one input parameter and return a boolean - true or false.

```csharp
static bool IsUpperCase(string str)
{
    return str.Equals(str.ToUpper());
}

static void Main(string[] args)
{
    Predicate<string> isUpper = IsUpperCase;

    bool result = isUpper("hello world!!");

    Console.WriteLine(result);
}
```

