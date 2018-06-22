## Implement an efficient sort Algorithm . What is it’s complexity ?
Quick-sort has O(n^2) worst-case runtime and O(n log n) average case runtime and it is also in-place . 

Quick sort is widely considered as the de-facto algorithm for sort.

## What is event Bubbling and capturing in JavaScript.
Event bubbling and capturing are two ways of event propagation in the HTML DOM API. When an event occurs in an element inside another element, and both elements have registered a handle for that event, the event propagation mode determines in which order the elements receive the event.

With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

With capturing, the event is first captured by the outermost element and propagated to the inner elements.
Using addEventListener with last argument true is only the way to catch the event at capturing .

## Explain Promise. What purpose it’s solving and how it’s different from callback ?
Promise helps us avoid nested call back functions (resulting in incomprehensible code) when there are multiple async function calls are dependent of each other’s returned value .

It has 3 states: pending, fulfilled and rejected

## Difference between Function Call and Apply in javaScript.
Apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly. 
A useful mnemonic is “A for array and C for comma.”

## What is the low level difference between Slice and Splice methods.
Splice is a mutating function , it modifies the array itself, and slice is non-mutating it creates a new array and returns that.

## How will you sort an array containing just [1.11, 0.2, 3, 11] in ascending order.
JavaScript `sort` does lexical sorting , so it’s converting the numbers to string before sorting . We need to pass a custom method to sort.

```
[1.11, 0.2, 3, 11].sort(function(a, b){
 return (a — b);
});
```
