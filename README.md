# React useEffect setInterval memory leak

This repository demonstrates a common bug in React applications involving the `useEffect` hook and the `setInterval` function.  The bug causes a memory leak because the interval is not cleared when the component unmounts.

The `bug.js` file contains the buggy code.  The `bugSolution.js` file shows the corrected code.

## Bug
The bug lies in the `useEffect` hook.  `setInterval` is used without a cleanup function to stop the interval when the component is unmounted. This causes the interval to continue running even after the component is removed from the DOM, leading to a memory leak.

## Solution
The solution is to use the return value of `useEffect` to provide a cleanup function that calls `clearInterval` when the component unmounts.