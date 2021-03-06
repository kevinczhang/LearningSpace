---
description: 'Extension methods, as the name suggests, are additional methods.'
---

# Extension Method

Extension methods allow you to inject additional methods without modifying, deriving or recompiling the original class, struct or interface. 

An extension method is actually a special kind of static method defined in a static class.

{% hint style="info" %}
LINQ is built upon extension methods that operate on IEnumerable and IQeryable type.
{% endhint %}

```csharp
using System; 

namespace ExtensionMethod { 
	class Geek {
		public void M1() { 
			Console.WriteLine("Method Name: M1"); 
		}
	}
} 

```

```csharp
using System; 

namespace ExtensionMethod { 

	// This class contains M4 method which we want to add in Geek class. 
	// NewMethodClass is a static class 
	static class NewMethodClass {
		public static void M4(this Geek g) 
		{ 
			Console.WriteLine("Method Name: M4"); 
		}
	}

	public class GFG {
		public static void Main(string[] args) { 
			Geek g = new Geek(); 
			g.M1();
			g.M4();
		} 
	} 
} 

```

{% hint style="info" %}
Points to Remember :

1. Extension methods are additional custom methods which were originally not included with the class.
2. Extension methods can be added to custom, .NET Framework or third party classes, structs or interfaces.
3. The first parameter of the extension method must be of the type for which the extension method is applicable, preceded by the **this** keyword.
4. Extension methods can be used anywhere in the application by including the namespace of the extension method
{% endhint %}

