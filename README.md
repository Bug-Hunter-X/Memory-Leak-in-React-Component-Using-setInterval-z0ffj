# React setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` within the `useEffect` hook without proper cleanup. This leads to a memory leak because the interval continues to run even after the component unmounts.

## Bug

The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks a cleanup function to stop the interval when the component is unmounted, resulting in a memory leak.

## Solution

The `bugSolution.js` file provides the corrected version.  It uses the return value of `useEffect` to implement a cleanup function that calls `clearInterval` when the component is unmounted, preventing the memory leak.

## How to reproduce
1. Clone this repo
2. Run `npm install`
3. Run `npm start`
4. Observe the counter in the browser, and then unmount the component (e.g., by navigating away from the page). Even after unmounting, the counter will continue updating in the console (only in the bug version).