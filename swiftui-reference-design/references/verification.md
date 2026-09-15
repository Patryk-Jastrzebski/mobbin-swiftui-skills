# Verify the SwiftUI deliverable

## Establish available tools

On macOS, inspect the selected Xcode version, real workspace/project, shared schemes and available simulator destinations. Prefer the project's existing build/test instructions. Do not invent a scheme or booted device. Build for a simulator without modifying signing accounts. Use the simulator device identifier explicitly when several devices are running.

Useful discovery commands, where available:

```sh
xcodebuild -version
xcrun simctl list devices available
```

Run xcodebuild -list against the discovered project/workspace, then build with its scheme and an available simulator destination. Preserve the actual exit result and relevant diagnostics. Do not label source review or Swift parsing on Linux as an iOS build.

## Visual and interaction checks

Launch the actual app using the environment's supported tooling. Capture and open screenshots; compare layout and hierarchy with selected reference evidence. Exercise the changed flow, including back, cancel, skip, validation, retry and rapid taps. Check safe areas and persistent CTA placement.

For motion-sensitive changes, record the relevant complete flow and inspect it at normal speed and around suspicious transitions. Do not claim that simctl alone can tap/type or that screenshot capture exercises interactions.

Verify Reduce Motion for custom motion. Force relevant loading/empty/error/offline states rather than checking only populated screens.

Specifically verify completed onboarding/authentication cannot be re-entered through stale navigation, optional gates return to the originating feature, cancelled/pending/failed purchases do not grant access, and relaunch restores only intended persisted state. Limit purchase testing to supported test environments.

## Completion report

Distinguish:
- Source implementation and static review.
- Successful Xcode build and actual tests run.
- Visually inspected screenshots/previews.
- Exercised simulator interactions and motion.
- Physical-device profiling, if actually performed.

When tooling is missing, state the pending checks and how to run them using the discovered project details; do not invent test results. Recheck after meaningful fixes. Stop when task-specific acceptance criteria are met and remaining risks are stated.
