---
description: >-
  The C# language's exception handling features help you deal with any
  unexpected or exceptional situations that occur when a program is running.
---

# Exception

 There are two main classes for exceptions - **SystemException** and **ApplicationException:**

* SystemException is a base class for all CLR generated errors.
* ApplicationException serves as a base class for all application related exceptions, which you want to raise on business rule violation.

![](../.gitbook/assets/image%20%2822%29.png)

### Important Exception Classes:

The following table lists important exception classes available in .Net.

| Exception | Description |
| :--- | :--- |
| ArgumentException | Raised when a non-null argument that is passed to a method is invalid. |
| ArgumentNullException | Raised when null argument is passed to a method. |
| ArgumentOutOfRangeException | Raised when the value of an argument is outside the range of valid values. |
| DivideByZeroException | Raised when an integer value is divide by zero. |
| FileNotFoundException | Raised when a physical file does not exist at the specified location. |
| FormatException | Raised when a value is not in an appropriate format to be converted from a string by a conversion method such as Parse. |
| IndexOutOfRangeException | Raised when an array index is outside the lower or upper bounds of an array or collection. |
| InvalidOperationException | Raised when a method call is invalid in an object's current state. |
| InvalidCastException | Raised when incompitible types are being converted. |
| KeyNotFoundException | Raised when the specified key for accessing a member in a collection is not exists. |
| NotSupportedException | Raised when a method or operation is not supported. |
| NullReferenceException | Raised when program access members of null object. |
| OverflowException | Raised when an arithmetic, casting, or conversion operation results in an overflow. |
| OutOfMemoryException | Raised when a program does not get enough memory to execute the code. |
| StackOverflowException | Raised when a stack in memory overflows. |
| TimeoutException | The time interval allotted to an operation has expired. |

Every exception class in .Net is derived from the base Exception class. It includes the following important properties using which you can use to get information about the exception when you handle the exception.

| Property | Description |
| :--- | :--- |
| Message | Provides details about the cause of the exception. |
| StackTrace | Provides information about where the error occurred. |
| InnerException | Provides information about the series of exceptions that might have occurred. |
| HelpLink | This property can hold the help URL for a particular exception. |
| Data | This property can hold arbitrary data in key-value pairs. |
| TargetSite | Provides the name of the method where this exception was thrown. |

