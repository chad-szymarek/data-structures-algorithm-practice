# BigO

## Why do we need BigO?

- BigO helps people talk about code and rank how well code runs.
- It lets us have a notation to help us talk about how a piece of code is running.

## Why does it matter?

- It's important to have a precise vocabulary to talk about how our code performs
- Useful for discussing trade-offs between different approaches
- When the code is slowing down or crashing, this helps identifying parts of the code that are inefficient

## BigO example

```javascript
function addUpTo(n) {
  let total = 0;
  /* The simple operations for this function are -
    addition with the total, but we do that addition for as big as the number that is coming in as an argument, is
    addition also with i
    there are a bunch of other calculations as well
  */
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}

/* This function's time complexity grows with n. The bigger n becomes, the more simple calculations need to be done
    We write this as O(n) */
```

```javascript
function addUpTo(n) {
  /* The simple operations for this function are -
        1 multiplication
        1 addition
        1 division
    */
  return (n * (n + 1)) / 2;
}

/* This function is contant time. No matter what n is, it performs the same amount of operations.
We represent this by O(1) */
```

## What does 'better' actually mean?

It usually means, "Is it faster? Is it less memory-intensive?"

## What do we count to see the speed of our code?

We count the number of simple operations that the computer performs.

## How to simplify BigO expressions

- We do not care about contants

  - O(2n) becomes O(n)
  - O(500) becomes O(1)
  - O(12n^2) becomes O(n^2)

- Smaller terms don't matter
  - O(N + 10) becomes O(n)
  - O(1000n + 50) becomes O(n)

1. Arithmetic operations are constant
2. Variable assignment is constant
3. Accessing elements in an array (by index) or object (by key) is constant
4. In a loop, the complexity is the length of the loop times the complexity of whatever happens inside of the loop

# Space Complexity

- We focus on auxiliary space complexity. Which means we care about the space required by the algorithm.
- We don't worry about the inputs

## Space Complexity in JS

- Most primitives (booleans, numbers, undefined, null) are constant space
- Strings require O(n) space (where n is the string length)
- Reference types are generally O(n), where n is the length (forarrays) or the number of keys (for objects)

## Example

```javascript
function sum(arr) {
  let total = 0;
  for (let i = 0; i < arr.length; i++) {
    total += arr[i];
  }
  return total;
}
/* 
we have a variable, total
we another variable, i
This means we have constant space O(1).
*/
```
