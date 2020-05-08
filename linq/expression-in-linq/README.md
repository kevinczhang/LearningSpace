---
description: >-
  LINQ introduced the new type called Expression that represents strongly typed
  lambda expression.
---

# Expression in LINQ

It means lambda expression can also be assigned to Expression&lt;TDelegate&gt; type.  The .NET compiler converts the lambda expression which is assigned to Expression&lt;TDelegate&gt; into an [Expression tree](https://www.tutorialsteacher.com/linq/expression-tree) instead of executable code. This expression tree is used by remote LINQ query providers as a data structure to build a runtime query out of it \(such as LINQ-to-SQL, EntityFramework or any other LINQ query provider that implements IQueryable&lt;T&gt; interface\).

![Expression and Func](../../.gitbook/assets/image%20%2817%29.png)

## Define an Expression

```csharp
Expression<Func<Student, bool>> isTeenAgerExpr = s => s.Age > 12 && s.Age < 20;
Expression<Action<Student>> printStudentName = 
                                s => Console.WriteLine(s.StudentName);
```

### Invoke an Expression



```csharp
Expression<Func<Student, bool>> isTeenAgerExpr = s => s.Age > 12 && s.Age < 20;

//compile Expression using Compile method to invoke it as Delegate
Func<Student, bool>  isTeenAger = isTeenAgerExpr.Compile();
            
//Invoke
bool result = isTeenAger(new Student(){ StudentID = 1, 
                                    StudentName = "Steve", Age = 20});
```



