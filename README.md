# React Router v6 Catch-all Route Unexpected Behavior

This repository demonstrates a subtle issue with catch-all routes (`/*`) in React Router v6.  The catch-all route appears to be intercepting all other routes, regardless of their order in the `Routes` component.  This is unexpected and can lead to difficulty in creating 404 pages that only appear when no other route matches.

## Bug Description

The provided `App.js` shows a basic React Router setup with three routes: `/`, `/about`, and the catch-all `/*`.  Despite the `/about` route being defined before the catch-all route, the catch-all route always intercepts requests for `/about`, resulting in the 'Not Found' component being displayed instead of the 'About' component.

## Solution

The `AppSolution.js` demonstrates the solution to this problem. By using the `useLocation` hook and checking the pathname, we can conditionally render different components based on the route.