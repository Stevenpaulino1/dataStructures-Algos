# Big O Notation

- A way of generalizing code and its performance
- Numeric representation of the performance
- useful for discussing tradeoffs between different approaches

- What does better mean?

  - Faster
  - Less memory intensive
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
- Access -> O(1) --> doesn't matter how long the array is, access goes direct when you provide its position

#Algorithms and Problem solving patterns
##Objectives

- Define what an Algorithm is
- Devise a plan to solve Algorithms
- Compare/contrast problem solving patterns including:
  - frequency counters,
  - Two pointer problems
  - Divide and Conquer

## What is an Algorithm?

- A process of set of steps to accomplish a certain task
- How do you improve?
  - Devise a plan for solving
  - Master Common problem solving patterns

## Problem Solving Strategies

- Understand the problem
- Explore concrete examples
- Break it down
- Solve & Simplify
- Look back and refactor

### Understand the Problem

- Can I restate the problem in my own words?
- What are the inputs that go in the problem?
- What should the outputs be?
- Can the outputs be determined from the inputs? Do I have enough information to solve the problem?
- How should i label the important parts

### Explore Concrete examples

- Coming up with the examples can help you better understand the problem. i.e "If the input is xyz, the output should be abc?"
- Sanity checks about how your solution should work
- Start with simple examples
- Progress to more complex examples
- Explore empty inputs
  - ex: Write a function which takes in a string, returns count of each character in a string.

### Break it Down

- Explicitly write out the steps you need to take

  - ex: function charCount(str){
    //make object to return @ end
    //loop over string and for each char
    // if char is number/letter AND is key in obj, add 1 to count
    // is char is number/letter AND is not key in obj, add to object, set value to one
    // if char is something else(space, period, etc) dont do anything
    return obj at the end

  }

### Solve and Simplify

- Solve the problem. If you can't, solve a simpler problem.
- Simplify
  - Find the core difficulty in what you're trying to do
    - Temp ignore that
    - Write simplified solution
    - Incorporate he difference back in

### Look back and refactor

- Can you improve performance?
- Can you resolve the result differently?

# Problem Solving Patterns

- Devise a plan for solving problems
- Master common problem solving patterns

## Frequency Counters

- This pattern uses objects or sets to collect values/ frequencies of values
- This can often avoid the need for nested loops or quadratic operations with arrays or strings
- Anytime you have multiple pieces of data and would need to compare them in particular
  - i.e, anagrams, consists of same digits

## Multiple Pointers

- Creating pointers or values that correspond to an index or position and move towards the beginning, middle, end base on a certain condition
- very efficient for solving problems with minimal space complexity as well.

## Sliding Window

- This pattern involves creating a window which can either be an array or number from one position to another
- Depending on a certain condition, the window either increases or closes, and a new window is created
- Very useful for keeping track of a subset of data in array or string
- example: finding the longest sequence of unique characters

## Divide and Conquer

- This pattern involves dividing a data set into smaller chunks and then repeating a process with a subset of data
- This pattern can tremendously decrease time complexity
