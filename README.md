# Firebase onAuthStateChanged Listener Memory Leak in React

This repository demonstrates a common issue when using Firebase's `onAuthStateChanged` listener within a React component.  Improperly detaching the listener can lead to memory leaks and unexpected behavior.  The `bug.js` file showcases the problem, while `bugSolution.js` provides the corrected code.

## Problem

The `onAuthStateChanged` listener, if not properly unsubscribed from when the component unmounts, continues to run even after the component is removed from the DOM. This results in memory leaks and potential unexpected behavior as the listener continues to listen for authentication state changes.

## Solution

The solution involves using React's `useEffect` hook with a cleanup function to ensure the listener is detached when the component unmounts. This cleanup function is executed when the component is unmounted or when the dependencies of the effect change.