# Expression Tree

Expression tree as name suggests is nothing but expressions arranged in a tree-like data structure. Each node in an expression tree is an expression.

Expression tree is an in-memory representation of a lambda expression. It holds the actual elements of the query, not the result of the query.

```csharp
ParameterExpression pe = Expression.Parameter(typeof(Student), "s");

MemberExpression me = Expression.Property(pe, "Age");

ConstantExpression constant = Expression.Constant(18, typeof(int));

BinaryExpression body = Expression.GreaterThanOrEqual(me, constant);

var ExpressionTree = Expression.Lambda<Func<Student, bool>>(body, new[] { pe });

Console.WriteLine("Expression Tree: {0}", ExpressionTree);
		
Console.WriteLine("Expression Tree Body: {0}", ExpressionTree.Body);
		
Console.WriteLine("Number of Parameters in Expression Tree: {0}", 
                                ExpressionTree.Parameters.Count);
		
Console.WriteLine("Parameters in Expression Tree: {0}", ExpressionTree.Parameters[0]);
```

![](../../.gitbook/assets/image%20%282%29.png)

### Why Expression Tree?

An expression tree is transparent. You can retrieve a parameter, return type and body expression information from the expression.

