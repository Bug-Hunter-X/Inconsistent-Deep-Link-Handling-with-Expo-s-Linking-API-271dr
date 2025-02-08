# Expo Linking API Event Listener Inconsistency

This repository demonstrates a bug related to the inconsistent behavior of Expo's `Linking.addEventListener` for handling deep links.  The issue primarily affects Android but can also occur on iOS under specific conditions.

The core problem is that the event listener registered with `Linking.addEventListener` may not consistently fire when deep links are opened, particularly when the app is in the background or launched for the first time. This leads to missed deep links and unexpected behavior in the application.

## Steps to Reproduce

1. Clone this repository.
2. Run the app on both Android and iOS simulators/devices.
3. Open a deep link that triggers the `url` event. Observe whether the event is handled consistently.
4. Test scenarios with the app in the background and after cold start.

## Expected Behavior

The event listener should consistently fire regardless of the app state and always correctly handle received deep links.

## Actual Behavior

The event listener frequently misses or delays events, particularly in Android, preventing the app from responding to deep links as intended.

## Solution

The provided solution explores alternative methods for handling deep links, mitigating the inconsistencies of the standard `Linking.addEventListener` approach.   See `bugSolution.js` for a potential fix.