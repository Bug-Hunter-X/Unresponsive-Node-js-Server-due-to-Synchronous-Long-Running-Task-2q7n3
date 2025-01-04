# Unresponsive Node.js Server

This repository demonstrates a common issue in Node.js where a long-running synchronous operation blocks the event loop, causing the server to become unresponsive.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Bug

The server performs a 5-second CPU-bound task synchronously within the request handler.  During this time, the event loop is blocked, and no other requests can be processed.  This leads to unresponsiveness and a poor user experience.

## Solution

The solution involves refactoring the code to use asynchronous operations (e.g., using `setTimeout` or other asynchronous patterns). This allows the event loop to continue processing other requests while the long-running task is executed in the background.