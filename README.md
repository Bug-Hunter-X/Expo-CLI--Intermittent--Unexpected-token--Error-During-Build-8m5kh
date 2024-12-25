# Expo CLI: Intermittent "Unexpected token" Error During Build

This repository demonstrates an uncommon bug encountered while using Expo CLI to build a React Native application. The error, "Unexpected token", appeared intermittently during the build process and was difficult to debug due to its inconsistent reproducibility. The issue seemed to be related to asynchronous data fetching and rendering within a specific component. 

## Bug Description

The error manifested as an "Unexpected token" message during the Expo build process.  It was not consistently reproducible, occurring more frequently under conditions of high network latency or when dealing with large datasets. The component involved asynchronous API calls to fetch and render data. No obvious syntax errors were present in the code.

## Reproduction Steps

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install`.
4. Run `expo start`. 
5. Attempt to build the app using `expo build:android` or `expo build:ios`. The error may not occur every time.

## Solution

The solution involved thorough review of asynchronous operations and error handling. The improved code includes robust error handling within the asynchronous functions which gracefully handle network errors.  The problem likely resulted from an unhandled exception in a asynchronous callback, causing the build process to terminate prematurely with a generic "Unexpected token" error.

