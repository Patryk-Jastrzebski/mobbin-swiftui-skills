# SwiftUI implementation decisions

## Navigation

| User relationship | SwiftUI starting point |
| --- | --- |
| Drill into detail | NavigationStack and value-based destinations |
| Top-level peer destinations | TabView; preserve each tab's navigation state |
| Independent task | sheet with its own NavigationStack when multi-step |
| Short selection or filters | sheet with supported presentation detents, or native Picker/Menu |
| Immersive task | fullScreenCover with a clear exit |
| Destructive choice | confirmationDialog or alert, based on context |
| Item actions | Menu, contextMenu or appropriate swipeActions |

These are semantic choices, not rules inferred from screenshots. Use NavigationSplitView for adaptive multi-column iPad experiences when the product supports them. Verify API availability against the deployment target and SDK.

Prefer identifiable routes and enum-based modal destinations over unrelated booleans. Keep native Back and edge-swipe behavior; do not hide the system back button merely to reproduce a screenshot. Change the app's root state after completed onboarding or mandatory sign-in and clear obsolete paths. Optional sign-in or paywalls should dismiss to the original action context. Resolve restored session state before choosing a root to avoid flashing Login.

Deep links must validate the destination and current access state; preserve pending intent through authentication. Do not expose every internal transient state as a route. Use interactiveDismissDisabled only for a justified unsaved-work or critical-operation case, with a visible safe exit/recovery path. It controls modal dismissal, not NavigationStack pop gestures. Do not assume active-tab reselect pops to root automatically; implement it only when part of the intended behavior.

## State and data

For iOS 17+ projects using Observation, use @Observable models, @State for view-owned observable instances and local values, and @Bindable where bindings to observable properties are needed. For older targets or established Combine architecture, preserve ObservableObject with @StateObject/@ObservedObject ownership. Do not mix ownership styles gratuitously or impose MVVM/TCA on a small existing feature.

Keep ephemeral focus, selection and presentation state local. Use @Binding for state owned elsewhere. Keep business operations and network services outside view body; use async/await and .task/.task(id:) for lifecycle-aware work with cancellation and stale-result handling. UI-facing mutations must use appropriate main-actor isolation. Async alone does not move expensive synchronous work off the main actor.

Use the project's persistence layer. @AppStorage suits small preferences, not secrets or a database; credentials belong in Keychain. Use SwiftData only where target availability and the data model justify it; preserve Core Data or existing storage otherwise. Persist onboarding completion at its defined completion event, not just when the final screen appears.

## Controls and layout

Use Button, Toggle, Picker, DatePicker, Slider, Form/List, .searchable and .refreshable where appropriate. Use PhotosPicker, ShareLink or system-controller bridges for relevant platform tasks. Keep native control semantics.

Use @FocusState, textContentType, keyboardType, submitLabel and onSubmit for input flows. Keep visible field labels and specific inline errors. Preserve keyboard-safe-area behavior; consider safeAreaInset for persistent bottom actions. Do not apply ignoresSafeArea to the entire interactive hierarchy to match edge-to-edge reference art.

Use List for conventional lists and ScrollView with lazy containers for custom feeds when warranted; neither choice removes the need to profile. Use stable model IDs, not generated UUIDs during rendering. Keep decoding, sorting and expensive formatting out of body and avoid geometry feedback loops. Format prices and dates using localized format styles and actual StoreKit display values where relevant.

## Motion and performance

Use native transitions first, scoped withAnimation or animation(_:value:) for custom changes. Prefer stable identity and interruptible state transitions. For custom gestures, use gesture state and supported predicted-end information deliberately; do not paste Reanimated spring constants into SwiftUI. Reserve matchedGeometryEffect or newer navigation transitions for justified continuity and verify their availability and behavior.

Read accessibilityReduceMotion and reduce spatial effects accordingly. Verify custom motion under interrupted gestures and rapid input. Use supported sensoryFeedback or UIKit feedback generators where appropriate without duplicating feedback the system already supplies.

Measure identified performance problems with Instruments on a representative device and release configuration. Distinguish simulator smoothness from device frame pacing. Do not claim a universal 60/120 fps result from a recording. Optimize measured main-thread work, image decoding, data fetching or unnecessary invalidation, then remeasure the same interaction.

## Primary references

- https://developer.apple.com/documentation/swiftui/managing-model-data-in-your-app
- https://developer.apple.com/documentation/swiftui/navigationstack
- https://developer.apple.com/documentation/swiftui
- https://developer.apple.com/design/human-interface-guidelines

Consult current documentation for exact availability and signatures; this file intentionally avoids pinning the user to a particular SDK version.
