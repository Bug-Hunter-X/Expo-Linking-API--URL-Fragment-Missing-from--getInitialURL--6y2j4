# Expo Linking API: URL Fragment Handling Bug

This repository demonstrates a bug in Expo's `Linking` API related to handling URLs with fragments.  The `Linking.getInitialURLAsync()` method does not consistently return the complete URL when a URL fragment is present.  This can lead to issues when attempting to parse and use the full deep link information within your application.

## Bug Reproduction

The `bug.js` file contains code that attempts to retrieve the initial URL and log it to the console.  When the app is launched with a deep link containing a fragment (e.g., `myapp://route#fragment`), the fragment is missing from the logged URL.

## Solution

The `bugSolution.js` file demonstrates a workaround that involves listening for `Linking.addEventListener` to receive the full URL with the fragment. This approach ensures that the complete URL is processed, regardless of the limitations of `getInitialURLAsync`.