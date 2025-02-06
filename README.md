# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling when dealing with user input. Specifically, this example showcases a scenario where a route handler attempts to parse a user ID as an integer without handling the case where the ID is not a number.

## Bug

The `bug.js` file contains the erroneous code.  It attempts to find a user based on an ID from the request parameters. However, it does not handle cases where `req.params.id` is not a valid integer, which can lead to exceptions or unexpected behavior.

## Solution

The `bugSolution.js` file demonstrates the corrected code. It includes error handling to check if `req.params.id` is a valid integer and returns a 400 Bad Request if it is not.  It also handles the case where the user is not found, returning a 404 Not Found response.

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `npm install express`.
4. Run `node bug.js` and then make a request to `/users/abc` (or other non-numeric values).  You'll see an error.
5. Run `node bugSolution.js` and make the same request. You will get a 400 Bad Request response.
