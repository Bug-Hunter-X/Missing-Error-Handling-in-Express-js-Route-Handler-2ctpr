# Express.js Route Handler Bug

This repository demonstrates a common bug in Express.js route handlers: the lack of proper error handling when dealing with user input.  The `bug.js` file shows a route handler that attempts to retrieve a user by ID.  However, it doesn't handle the scenario where the ID is not a valid integer or if the user is not found.

The `bugSolution.js` file provides a corrected version with robust error handling.

## Bug

The original code attempts to parse the `userId` as an integer without checking for errors. If the `userId` parameter is not a valid integer, the `parseInt()` function will return `NaN`, causing a potential crash or unexpected behavior in the `find()` method.

## Solution

The solution adds error handling to check if the `userId` is a valid integer and if the user exists.  If either condition is false, a 404 error is returned.