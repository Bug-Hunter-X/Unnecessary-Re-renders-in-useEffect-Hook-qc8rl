# Unnecessary Re-renders in useEffect Hook

This repository demonstrates a common React bug where the `useEffect` hook causes unnecessary re-renders. The `useEffect` hook is triggered on every render due to a missing dependency array.  This leads to performance issues and unnecessary console output.

## Bug Description

The `MyComponent` component uses the `useState` hook to manage a count.  The `useEffect` hook logs the count to the console.  However, the dependency array is empty (`[]`), meaning the effect runs after every render, even though the only dependency is `count`, which is not explicitly included in the dependency array. This causes the console log to repeatedly output the current count value.

## Solution

The solution is to include `count` in the dependency array. This ensures the effect only runs when the `count` value changes. 