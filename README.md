# React useEffect Dependency Array Bug

This repository demonstrates a common yet subtle bug in React's `useEffect` hook: incorrectly specifying the dependency array, leading to stale closures and unexpected behavior.

## Bug Description

The `useEffect` hook is used to perform side effects after rendering.  However, if the dependency array is not correctly specified, it can lead to unexpected behavior. In this case, the effect only runs once, when the component mounts, instead of whenever the `count` variable changes.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that the console message 'Component rendered!' only appears once when the component initially renders. Incrementing the counter doesn't trigger a new log. This is because the `count` variable is not included in the dependency array.

## Solution

The solution involves correctly defining the dependency array to include `count`.  This ensures the `useEffect` hook runs whenever `count` changes.

## Additional Notes

This example highlights the importance of carefully considering and specifying dependencies in `useEffect` to ensure predictable behavior in React components.