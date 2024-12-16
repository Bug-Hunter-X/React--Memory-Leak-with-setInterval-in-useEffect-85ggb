# React: Memory Leak with setInterval in useEffect

This repository demonstrates a common mistake when using `setInterval` within a React component's `useEffect` hook: forgetting to clear the interval when the component unmounts.  This leads to memory leaks and can cause unexpected behavior.

## The Bug

The `bug.js` file contains a React component that increments a counter every second using `setInterval`. However, it fails to clear the interval when the component is unmounted, resulting in the interval continuing to run in the background, even after the component is no longer rendered.  This consumes resources and may cause unexpected updates.

## The Solution

The `bugSolution.js` file provides the corrected code.  The key change is adding a cleanup function to the `useEffect` hook that calls `clearInterval` to stop the interval when the component is unmounted. This prevents memory leaks and ensures the component behaves as expected.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the counter in your browser.
5. Navigate away from the page or unmount the component.  The leaked interval will continue updating the counter even when the component is not visible.
6. Test the `bugSolution.js` for the fix. 