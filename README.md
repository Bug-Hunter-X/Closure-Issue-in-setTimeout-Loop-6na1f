# JavaScript Closure Issue in `setTimeout` Loop

This repository demonstrates a common JavaScript closure issue within a `setTimeout` loop.  The problem arises from how closures capture variables in their surrounding scope. In this example, the `console.log(i)` statement always prints the final value of `i` (10), instead of the value of `i` at the time `setTimeout` was called.

## Bug Description
The expected output of the code in `bug.js` would be to log the numbers 0 through 9. However, due to the closure, it logs 10 ten times. This is because the `setTimeout` callback function only captures the reference to `i`, not its value at the time of its creation. By the time the `setTimeout` function executes, the loop has already completed, and `i` is 10.

## Solution
The `bugSolution.js` file provides a fix by using an Immediately Invoked Function Expression (IIFE) to create a new scope for each iteration, effectively capturing the current value of `i`.