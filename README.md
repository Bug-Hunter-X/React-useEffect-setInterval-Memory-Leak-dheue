# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The issue is a memory leak caused by failing to properly clean up the interval when the component unmounts.

## Problem

The `bug.js` file contains a component that uses `setInterval` to update a counter every second.  However, it's missing a crucial cleanup function within the `useEffect` hook. This means the interval continues to run even after the component is unmounted, leading to a memory leak.

## Solution

The `bugSolution.js` file provides a corrected version.  It uses a return statement inside the `useEffect` to clear the interval using `clearInterval` before the component unmounts, preventing the memory leak.