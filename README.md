# React useEffect Infinite Loop with setInterval

This repository demonstrates a common mistake when using the `useEffect` hook in React with `setInterval`. Incorrectly including the state variable in the dependency array leads to an infinite loop.

## Bug
The `bug.js` file contains the buggy code. The `setInterval` function is set up to update the state `count` every second.  However, `count` is included in the dependency array of `useEffect`. This creates a loop: `count` updates, causing a re-render, which triggers the effect again, updating `count` again, and so on.

## Solution
The `bugSolution.js` file shows the corrected code. The dependency array for the `useEffect` hook is empty (`[]`). This ensures the `setInterval` is only set up once when the component mounts and is cleared when the component unmounts.