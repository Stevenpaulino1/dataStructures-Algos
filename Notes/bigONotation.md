# Big O Notation

- A way of generalizing code and its performance
- Numeric representation of the performance
- useful for discussing tradeoffs between different approaches

- What does better mean?

  - Faster
  - Less memory itensive
  - More readable

- The problem with time

  - Different and same machines will record different times ex
  - speed measurements may not be precise
  - i.e performance.now()

- Count the number of simple operations a computer has to perform
  - ex:
    Write a function that calculates the sum of all numbers from 1 up to and including n


      function addUpTo(n) {
        let total = 0;
        for (let i = 1; i <= n; i++) {
          total += i;
        }
        return total;
      }
      console.log(addUpTo(5));

       3 simple operations regardless of n

-------------------VS-------------------------

function addUpTo(n) { return (n \* (n + 1)) / 2; }

Regardless of exact number of operations, it grows proportionally with n, roughly

---

## Definition

- We can say that an Algorithm is o(f(n)).If the number of simple operations the computer has to do is eventually less than the constant times f(n), as n increases.

- f(n) could be:

  - linear (f(n)=n)
  - quadratic (f(n)= n2)
  - constant (f(n)=1)
  - or something completely different

  function printAllPairs(n){
  for (let i = 0; i< n; i++){
  for (let j = 0; j< n; j++){
  console.log(i,j)
  }
  }
  }

- o(n) operation inside of an o(n) operation => o(n)squared

## Simplifying Big O expressions

- When determining the time complexity of an Algorithm, some helpful rule of thumbs

  - Constants don't matter

    - O(2n) gets simplified to O(n) --> linear
    - O(500n) gets simplified to O(1) --> constant
    - O(13nsquared) simplified to O(n squared)

  - Smaller terms dont matter
    - O(n+10) => O(n)
    - O(n squared + 5n + 8)

## Space Complexity

- How can we analyze the runtime of an Algorithm

- Rules of thumb
  - Most primitives (booleans, numbers, undefined, null) are constant Space
  - Strings require O(n) space, where n is the string length
  - reference types generally o(n), n is length (arrays) or number of keys (for objects)
  - example, o(1) space, the two zeros

    function sum(arr){
    let total = 0;
    for (let i = 0; i < arr.length; i++){
    total += arr[i]
    } return total
    }
- Logarithms
  - inverse of exponents
  - two, to what power, equals 8?
  - log time complexity is great!

# Analyzing performance of arrays & objects

- When to use objects
  - When you don't need order
  - When you need fast access/insertion and removal

## Big o of objects

- When you don't need any ordering, objects are an excellent choice for looking for value
- Insertion -> O(1)
- Removal -> O(1)
- Searching -> O(n)
- Access -> O(1)

## Object Methods

- Objects are quick but no order to them
  - object.keys -> O(n)
  - object.value -> O(n)
  - object.entries -> O(n)
  - object.hasOwnProperty - O(1)
- Has to access as the object grows to put into array (the first 3)

## Arrays and when to use

- intrinsic order to them, when you need order

## Big O of Arrays

- Insertion -> It depends, have to re-index every element
- Removal -> It depends, have to re-index every element
- Searching -> O(n)
- Access -> O(1) --> doesn't matter how long the array is, access goes direct when you provide its positon
