---
description: 'For every thread, JVM creates a separate stack at the time of thread creation.'
---

# JVM Stack Area

The Java virtual machine only performs two operations directly on Java Stacks: it pushes and pops frames. After completing a method, corresponding entry from the stack is removed. After completing all method calls the stack becomes empty and that empty stack is destroyed by the JVM just before terminating the thread. 

And stack for a particular thread may be termed as **Run – Time Stack**. Each and every method call performed by that thread is stored in the corresponding run time stack including parameters, local variables, intermediate computations, and other data. 

The data stored in the stack is available for the corresponding thread and not available to the remaining threads. Hence we can say local data is thread safe. Each entry in the stack is called **Stack Frame** or **Activation Record**.

![](../.gitbook/assets/image%20%289%29.png)

##  **Stack Frame Structure**

The stack frame basically consists of **three** parts: **Local Variable Array, Operand Stack & Frame Data**. When JVM invokes a Java method, first it checks the class data to determine the number of words _\(size of the local variable array and operand stack, which are measured in words for each individual method\)_ required by the method in the local variables array and operand stack. It creates a stack frame of the proper size for invoked method and pushes it onto the Java stack.

###  **1. Local Variable Array \(LVA\):**

* The local variables part of stack frame is organized as a zero-based array of words.
* It contains all parameters and local variables of the method.
* Each slot or entry in the array is of 4 Bytes.
* Values of type int, float, and reference occupy 1 entry or slot in the array i.e. 4 bytes.
* Values of double and long occupy 2 consecutive entries in the array i.e. 8 bytes total.
* **Byte, short and char values will be converted to int type before storing** and occupy 1 slot i.e. 4 Bytes.
* But the way of storing Boolean values is varied from jvm to jvm. But most of the jvm gives 1 slot for Boolean values in the local variable array.
* The parameters are placed into the local variable array first, in the order in which they are declared.

### **2. Operand Stack \(OS\):**

* JVM uses operand stack as work space like rough work or we can say for storing intermediate calculation’s result.
* Operand stack is organized as array of words like local variable array. But this is not accessed by using index like local variable array rather it is accessed by some instructions that can push the value to the operand stack and some instructions that can pop values from operand stack and some instructions that can perform required operations.

###  **3. Frame Data \(FD\):**

* It contains all symbolic reference \(_constant pool resolution\)_ and normal method return related to that particular method.
* It also contains a reference to Exception table which provide the corresponding catch block information in the case of exceptions.

