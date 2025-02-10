# React Native useRef: Accessing current value before assignment

This repository demonstrates a common error when using the `useRef` hook in React Native: attempting to access the ref's current value before it's been assigned a value. This often leads to a `null` or `undefined` error.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides the corrected code with proper handling for the initial null value.

## Problem

The issue stems from accessing `myRef.current` within the `useEffect` hook or immediately after the ref's initialization.  At this point, the component's rendering hasn't completed, and thus the ref's value is not yet assigned.

## Solution

The solution involves ensuring the ref is assigned and populated before accessing its current value.  This typically requires using an effect hook with a conditional check to avoid attempting to access `myRef.current` while it remains null.