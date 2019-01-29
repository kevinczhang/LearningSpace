# Common Questions

##  **Explain Final keyword in java?**

The final keyword in java is used to restrict the user. The java final keyword can be used in many context. Final can be: Variable, method or class 

1\) Java final variable If you make any variable as final, you cannot change the value of final variable\(It will be constant\). 

2\) Java final method If you make any method as final, you cannot override it. 

3\) Java final class If you make any class as final, you cannot extend it.

##  **When is the super keyword used?**

super keyword is used to refer:

* immediate parent class constructor,
* immediate parent class variable,
* immediate parent class method.

##  **Can a top level class be private or protected?**

 Top level classes in java can’t be private or protected, but inner classes in java can. The reason for not making a top level class as private is very obvious, because nobody can see a private class and thus they can not use it. Declaring a class as protected also doesn’t make any sense. The only difference between default visibility and protected visibility is that we can use it in any package by inheriting it. Since in java there is no such concept of package inheritance, defining a class as protected is no different from default.



