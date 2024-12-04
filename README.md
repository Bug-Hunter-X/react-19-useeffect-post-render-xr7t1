# React 19 useEffect Bug

This repository demonstrates a common bug in React 19 related to the `useEffect` hook. The bug causes the effect to run after every render, leading to performance issues and unexpected behavior. 

## Bug Description

The provided `MyComponent` uses a `useEffect` hook without a dependency array (`[]`). This means that the effect runs after every render. The `console.log` statement will flood the console with messages, impacting performance. In more complex applications, this can lead to unpredictable behavior. 

## Solution

The solution is to specify the dependencies within the array. If the effect should run only when the `count` changes, the array should contain `[count]`. This ensures the effect runs only when the value of `count` is updated.

## How to reproduce

1. Clone this repository.
2. Run `npm install`
3. Run `npm start`
4. Observe the console output for frequent 'Count updated' messages

## How to fix

1. Replace `useEffect(() => { ... });` with `useEffect(() => { ... }, [count]);`
2. Restart the application
3. Observe that the messages are more controlled now, improving performance

