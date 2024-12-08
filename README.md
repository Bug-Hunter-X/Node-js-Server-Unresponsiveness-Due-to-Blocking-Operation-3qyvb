# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a server becomes unresponsive due to a long-running synchronous operation within the request handler.  The `server.js` file contains the buggy code.  The solution, `serverSolution.js`, demonstrates how to address this using asynchronous operations.

## Problem

Node.js is single-threaded.  When a long-running operation blocks the main thread (as in the example's `while` loop), no other requests can be processed. This leads to the server appearing unresponsive or hanging.

## Solution

The solution involves using asynchronous operations (like timers, promises, or async/await) to avoid blocking the main thread.  This allows Node.js to continue handling other requests while the long-running task executes in the background.