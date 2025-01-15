# Node.js Server Hang Issue

This repository demonstrates a common issue in Node.js where long-running operations can block the event loop, causing the server to become unresponsive.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a 5-second delay.  This blocks the event loop, preventing the server from handling other requests during this time.  Any new requests will hang until the long-running operation completes.

## Solution

The `serverSolution.js` file addresses this problem by using `setTimeout` to achieve the delay asynchronously.  This allows the event loop to continue processing other requests while the timer runs.