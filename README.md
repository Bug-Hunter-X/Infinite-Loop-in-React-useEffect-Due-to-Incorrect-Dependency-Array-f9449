# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook and its dependency array.  The example showcases an infinite loop caused by an incorrect dependency declaration within a nested `useEffect`.

## Bug Description

The primary issue lies in how the inner `useEffect` is set up.  It depends on the `count` state variable. Every time `count` updates, the inner `useEffect` triggers, logging a message to the console. This creates a loop.  React re-renders, the inner `useEffect` runs again, triggering another re-render and so on. 

## Solution

The solution involves correctly defining the dependencies for the inner useEffect. The dependency array should be empty (`[]`) if the effect should only run once after the initial render, or it should list the specific state variables it depends on.