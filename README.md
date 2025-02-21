# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common JavaScript error related to closures within `setTimeout` loops. The code intends to log numbers 0 through 9 with a one-second delay between each log. However, due to how closures work in JavaScript, it incorrectly logs the final value of the loop counter (10) ten times.

## The Problem

The issue lies in how the `setTimeout` callback function captures the loop variable `i`. By the time the `setTimeout` callbacks finally execute, the loop has already completed, and `i` is equal to 10. Therefore each callback logs this final value. This is a classic closure problem. 

## Solution

The solution involves using an immediately invoked function expression (IIFE) or `let` to create a new scope for each iteration, effectively capturing the correct value of `i` for each callback.

## How to Reproduce

1. Clone this repository.
2. Open `bug.js` in a browser's developer console or a Node.js environment.
3. Run `myFunction()`. Observe the incorrect output.
4. Open `bugSolution.js`.  Observe the correct output when `myFunction()` is called.