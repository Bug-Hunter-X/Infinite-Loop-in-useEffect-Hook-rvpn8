# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug where an infinite loop occurs within the `useEffect` hook. The bug arises from incorrectly updating the state variable within its dependency array, leading to continuous re-renders and an infinite loop.

## Bug Description

The provided `MyComponent` function uses the `useEffect` hook to increment a counter. The dependency array `[count]` is incorrect because updating `count` causes the effect to run again, which in turn updates `count`, creating an infinite loop. 

## Solution

The solution is to modify the state update logic. This can be done by using functional updates, which ensure the state updates are applied correctly based on the previous state. Also, you should remove the 'count' dependency from the useEffect.  The function `setCount` will only update the state after all the current state changes have completed.