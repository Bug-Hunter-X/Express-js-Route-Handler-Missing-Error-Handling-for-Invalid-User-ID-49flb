# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the example shows a route that fetches a user by ID, but fails to handle cases where the ID is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  It attempts to parse the user ID from the request parameters as an integer and uses it to find a user in an array.  If the ID is not a number, `parseInt` will return `NaN`, causing the `find` method to fail silently or throw an error, depending on the data structure used.

## Solution

The `bugSolution.js` file demonstrates how to improve the code by adding input validation and appropriate error handling.  It checks if the ID is a valid integer and returns a 400 Bad Request error if it is not.  If a user with the specified ID is not found, it returns a 404 Not Found error.