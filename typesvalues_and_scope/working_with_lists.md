# Working with Lists

Most javascript programs involve lists, or arrays. Understanding how to work with lists in a declarative and efficient way is important.

## Using `.map()`, `.reduce()` and `.filter()`

Making use of Javascript's `map()`, `reduce()` and `filter()` Array methods can help you write more declarative, fluent style code. Rather than building up `for` loops and nesting to process data in lists and collections, you can take advantage of these methods to better organize your logic into building blocks of functions, and then chain them to create more readable and understandable implementations.

Javascript's `Array.prototype` has a number of methods available to make working with lists easier. The primary one that most developers use is `.forEach()` for looping over items in a list.

Consider the process of adding 1 to each integer in a list:

```javascript
var numbers = [1,2,3,4,5,6,7,8,9,10];  
numbers.forEach((n, index) => {  
   numbers[index] = n + 1;
});
// => [2,3,4,5,6,7,8,9,10,11]
```

Here, we're looping through the array and adding one to each item. This approach also has the side effect that it mutates the original list of data.

### `.map()`

As good developers, we want to reduce side effects \(_avoid mutating state_\) and be more declarative with the code we're writing. We can do this using `.map()`.

```javascript
var addOne = (n) => n+1,
    plusone = numbers.map(addOne);  
// => numbers: [1,2,3,4,5,6,7,8,9,10]
// => plusone: [2,3,4,5,6,7,8,9,10,11]
```

Easy enough. Using `.map()` we get no side-effects \(_map does not alter the current list, it returns a new one_\) and we have a new list with exactly what we wanted.

### `.filter()`

We can use `filter()` to visit each item in a list, much like `map()`; however, the function you pass to `filter()` is a predicate that should return `true` to allow that item in the list, or `false` to skip it.

```javascript
var evens = plusone.filter((n) => n % 2 === 0);  
// => evens: [2,4,6,8,10]
```

Also like `map()`, `filter()` returns a new array with copies of the items that match the filter and does not modify the original.

### `.reduce()`

When we want to aggregate data in a list we can use `reduce()`. `reduce()` applies a function to an accumulated value on each element in a list from left to right.

```javascript
var byfour = evens.reduce((groups, n) => {  
  let key = n % 4 == 0 ? 'yes' : 'no';
  (groups[key] = groups[key] || []).push(n);
  return groups;
}, {});
// => byfour: { 'yes': [4,8], 'no': [2,6,10] }
```

Unlike `map()` and `filter()`, however, `reduce()` doesn't return a new list, it returns the aggregate value directly.

In the case of our number list, our accumulated value was the initial empty object passed as the last parameter to the `reduce()` call. We then used that to create a property based on the _divisible-by-four-ness_ of each number that served as a bucket to put the numbers in.

## Being fluent-ish

A fluent API or interface is one that provides better readability through:

1. chaining of method calls over some base context
2. defining operations via the return value of each called method
3. is self-referential, where the new context is equivalent to the last
4. terminates via return of a void context

_JQuery_ works likes this, as well as libraries like _lodash_ and _underscore_ using the `_.chain()` method wrapper, allowing chaining of method calls on a base context that represents a DOM element tree.

Because `map()` and `filter()` return new arrays, we can take advantage of this and chain multiple array operations together.

```javascript
[1,2,3,4,5,6,7,8,9,10]
  .map((n) => n*2)
  .filter((n) => 10 % n == 0)
  .reduce((sum, n) => (sum += n), 0);
// => 12
```

Now, this isn't a "_real_" fluent interface; but it does resemble one from a chaining perspective and gives us a more declarative approach to implementing operations on lists.

## Looping the old fashioned way

Sometimes we need our loops to be extremely efficient. Using `.map`, `.reduce` and `.filter` should be your first choice for a declarative implementation using lists; but, if you are dealing with large datasets \(_in the thousands or more_\), using a standard `for` or `while` loop will nearly always be faster.

### Efficiency

Using a `for` or `while` can be improved by caching the length of the list and potentially by working backwards if possible. Keep in mind that the three parts of a `for` loop occur at certain stages:

```text
for (var i=0; i < 10; i++)
```

The 1st expression happens only once, prior to iteration over the loop items. The 2nd expression is evaluated each time through the loop at the beginning of the loop block; and the 3rd expression is evaluated each time through the loop at the end of the loop block.

Realizing this, we can minimize the work the javascript compiler has to do by keeping the 2nd and 3rd expressions as simple to evaluate as possible \(_most modern browsers account for this fact and will properly optimize a_ `for` _loop regardless of how it is written today_\)

```javascript
var arr = [1,2,3,4];
for (var i=0, l = arr.length; i < l; i++) { ... }

var arr = [1,2,3,4],
    index = arr.length;

while (index--) {
   // do something with arr[index]
}
```

Keeping with the same concepts mentioned above, using a `while()` loop and working our index backwards also minimizes the number of expressions that need evaluating during the loop as well. This may or may not be possible depending on the needs of your program and data.

#### Looping through Objects

You can also loop through an Object's keys using a `for..in` loop. However, be sure that you use test each property using `.hasOwnProperty()`, otherwise you'll cycle through all the immediate properties on that object as well as all the properties in the object's prototype, and it's prototype, ad infinitum.

```javascript
 var obj = { 
    name: 'Nathon Fillion', 
    title: 'Cap\'n Tight Pants' 
 };
 for (var prop in obj) {
   if (obj.hasOwnProperty(prop)) {
     // do something with obj[prop]
     // prop is direct property on obj here
   }
 }
```

### Minimize the work done in loops

Clearly, doing lots of heavy processing inside a loop that might run for 10s of thousands of iterations is going to be an expensive operation. Try to minimize the amount of work you're doing inside a loop, especially any DOM manipulations.

```javascript
 var items = [],
     $list = $('ul.serenity'),
     names = ['Kaylee', 'Book', 'Wash', 'Zoe'];

 // GOOD: build fragments, append once outside loop
 //       use cached references to elements, instances
 for (var i=0, l=names.length; i < l; i++) {
   items.push($('<li/>').text(names[i]));
 }
 $list.append(items);

 // BAD: append multiple times inside loop
 //      don't cache a reference
 for (var i=0; i < names.length; i++) {
   $('ul.serenity').append($('<li/>').text(names[i]));
 }
```

### Exercises

