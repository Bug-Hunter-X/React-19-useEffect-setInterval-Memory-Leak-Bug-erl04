# React 19 useEffect setInterval Memory Leak Bug

This repository demonstrates a common bug in React 19 involving the use of `setInterval` within the `useEffect` hook without proper cleanup.  This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the buggy code.  The `bugSolution.js` demonstrates the correct implementation using `clearInterval` to prevent memory leaks.

## Bug Description
When using `setInterval` inside `useEffect`, it's crucial to clear the interval when the component unmounts or when the effect is no longer needed. Failure to do so can result in the interval continuing to run even after the component is gone, potentially leading to memory leaks and performance issues.

## Solution
The solution involves storing the return value of `setInterval` and using `clearInterval` in the cleanup function of the `useEffect` hook.