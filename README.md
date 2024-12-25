# Unhandled Error in Asynchronous Express.js Middleware

This repository demonstrates a common error in Node.js Express.js applications: unhandled errors in asynchronous middleware.  The `bug.js` file shows a server that can crash due to an unhandled error within a `setTimeout` callback. The solution is provided in `bugSolution.js`.

## Bug

The `bug.js` server simulates an asynchronous operation that might throw an error.  If the random number generated is less than 0.5, an error is thrown.  However, because this error occurs within an asynchronous callback, it's not caught by the standard Express.js error handling middleware, leading to a server crash.

## Solution

The `bugSolution.js` demonstrates the correct way to handle asynchronous errors by using a `try...catch` block within the asynchronous callback or utilizing a custom error handler middleware.