# Next.js 15 useEffect Cleanup Issue

This repository demonstrates a subtle bug related to the `useEffect` hook's cleanup function in a Next.js 15 application.  The counter on the `/about` page continues to increment even after navigating away from the page, indicating that the cleanup function, responsible for clearing the interval, isn't being executed correctly. This is a common issue when dealing with intervals and route changes.

## Reproduction
1. Clone the repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to `/about`.
5. Observe the counter incrementing.
6. Navigate away from `/about` (e.g., to `/`) and back.
7. The counter will resume incrementing from where it left off.

## Solution
The solution involves ensuring the cleanup function within the `useEffect` hook is called reliably during unmount or route transitions. A possible solution might involve using a custom hook or refactoring the interval management.  See the `aboutSolution.js` file for a potential fix.