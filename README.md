# Unhandled Promise Rejection in Express.js Route Handler

This repository demonstrates a common error in Express.js applications: unhandled promise rejections within route handlers.  Failing to properly handle these rejections can lead to application crashes or unexpected behavior.  The `bug.js` file showcases the problematic code, while `bugSolution.js` provides the corrected implementation.

## Problem

The `bug.js` file contains an Express.js route handler that performs an asynchronous operation. However, the `.catch()` block within the asynchronous operation only logs the error to the console and doesn't handle the rejection properly, allowing the application to continue running potentially in an inconsistent state.

## Solution

The `bugSolution.js` file shows the correct way to handle promise rejections.  Instead of just logging the error, the corrected code uses the `next()` function to pass the error to the Express.js error handling middleware. This ensures that the error is properly handled and prevents the application from crashing or displaying unexpected behavior.

## Setup

1. Clone the repository.
2. Run `npm install express`
3. Run the buggy code using `node bug.js` and observe the behavior.  Notice the error being printed to the console.
4. Run the solution code using `node bugSolution.js`.  The application will now handle errors gracefully.