# React 19 useEffect Bug

This repository demonstrates a subtle bug in React 19 related to the `useEffect` hook.  The `useEffect` hook, even with a dependency array, seems to run after every render, leading to performance problems and potentially unexpected side effects.

## Bug Description

The provided code is a simple counter component. The `useEffect` hook is intended to log a message to the console whenever the `count` state changes.  However, in React 19 (and potentially other versions), this effect runs after every render, regardless of the `count` value changing.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console output. You'll see that the 'Component rendered' message is logged more frequently than expected.

## Solution

The solution involves careful examination of the component's logic and dependencies. This issue might arise from a missing dependency in the `useEffect`'s dependency array or from the use of stale closures.  In this specific example, if you fix this the problem will dissapear.