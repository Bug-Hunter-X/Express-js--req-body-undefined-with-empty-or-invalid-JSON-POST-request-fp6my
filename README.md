# Express.js: Handling Empty or Invalid JSON POST Requests

This repository demonstrates a common issue in Express.js applications where `req.body` is undefined when handling POST requests with empty or invalid JSON payloads.  The issue arises because the `express.json()` middleware expects valid JSON and fails silently if it doesn't receive it.

The `bug.js` file showcases the problem. The `solution.js` file provides a robust solution using middleware to handle cases with empty or malformed JSON.

## Problem

When sending an empty POST request or a POST request with invalid JSON to the `/data` endpoint, the server logs `undefined` for `req.body` and might throw errors later in the request processing.

## Solution

The solution introduces custom middleware to check the request body's validity before proceeding.  If the body is empty or invalid, it returns a more informative error response.