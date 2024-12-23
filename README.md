# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js servers: unresponsiveness due to a long-running synchronous operation.  The server hangs because the event loop is blocked, preventing it from handling new requests.

## Problem

The `server.js` file contains a simple HTTP server.  The request handler includes a `while` loop that simulates a 5-second task.  This synchronous operation blocks the event loop, causing the server to become unresponsive during that time.  Any new requests will not be processed until the loop completes.

## Solution

The `serverSolution.js` file provides a solution using asynchronous operations.  Asynchronous tasks don't block the event loop, ensuring the server remains responsive.  This example utilizes `setTimeout` to simulate the long-running task.