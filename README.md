# React setInterval Memory Leak
This repository demonstrates a common error in React applications involving the improper use of `setInterval` within the `useEffect` hook.  The provided code creates a memory leak because the interval is never cleared when the component unmounts.

## Bug Description
The `MyComponent` uses `setInterval` to increment a counter every second. However, it fails to include a cleanup function in the `useEffect` hook to clear the interval when the component is unmounted.  This results in the interval continuing to run even after the component is no longer rendered, leading to a memory leak.

## Solution
The solution involves adding a cleanup function to the `useEffect` hook. This function uses `clearInterval` to stop the interval when the component unmounts.