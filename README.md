# React useEffect Hook Missing Dependency

This repository demonstrates a common bug in React applications: an infinite loop caused by a missing dependency in the `useEffect` hook.

## Bug Description

The `useEffect` hook is designed to perform side effects after every render. However, if the dependency array is missing or incorrect, the effect will run repeatedly, leading to an infinite loop and performance issues. In this example, the `count` variable is used within the effect, but it's not included in the dependency array.  This means that the effect runs every time the component re-renders, which causes `setCount` to be called repeatedly, triggering another re-render, and continuing the cycle.

## Bug Reproduction

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install the necessary dependencies.
4. Run `npm start` to start the development server.
5. Observe the infinite loop in the console and the extremely fast counter updating in the UI.

## Solution

The solution is to include `count` in the dependency array of the `useEffect` hook. This ensures that the effect only runs when the value of `count` changes.

## Learning Points

- Always carefully consider what dependencies you need in the useEffect hook.
- Understand how the dependency array controls when the effect function runs.
- Pay attention to console warnings for potential issues like this.