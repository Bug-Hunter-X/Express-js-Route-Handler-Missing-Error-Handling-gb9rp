# Express.js Route Handler Missing Error Handling
This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the provided code lacks error handling for a scenario where the user ID parameter (`req.params.id`) is not a valid number. This can lead to unexpected errors and crashes.

## Bug
The `bug.js` file contains the faulty code.  The route handler attempts to parse the `userId` as an integer using `parseInt()`, but it doesn't handle the case where `req.params.id` is not a number or is not a valid integer. This could lead to a runtime error, potentially crashing the application.

## Solution
The `bugSolution.js` file provides a corrected version of the code. This version includes explicit checks to ensure the `userId` is a valid integer before attempting to use it.  It handles the case where the user ID is invalid, returning a more graceful error response.

## How to reproduce the bug
1. Clone this repository.
2. Run `node bug.js`.
3. Send a GET request to `/users/abc` (or any non-numeric ID).  Observe the error.