---
name: swiftui-reference-design
description: Design, implement and refine native iOS apps and flows in SwiftUI from Mobbin references or supplied screenshots. Use for reference-driven SwiftUI screens, onboarding, paywalls, navigation, UI state and visual verification.
---
# SwiftUI Reference Design

Build native SwiftUI experiences from studied references. Use mobbin-design-research when available for reference discovery; supplied screenshots and an existing design system are equally valid inputs. Keep research-only, mockup-only and implementation tasks within the requested scope.

## Start with the real project

Inspect project instructions, source structure, Xcode project/workspace, supported devices, deployment target and existing architecture. Preserve working conventions. For a new project, disclose a reasonable deployment-target assumption and verify needed API availability; do not upgrade an existing minimum OS or migrate its architecture just for this skill.

Implement Swift and SwiftUI. Do not introduce Expo, React Native, web views as the UI shell, or JavaScript libraries. Use UIKit interoperability only when a concrete platform capability requires it. Read Apple documentation for unfamiliar or version-sensitive APIs.

## Reference to native design

Inspect reference images before adopting a pattern. Separate observed layout from proposed interactions; a still image cannot prove navigation or motion. Translate the pattern into the user's brand rather than reproducing another app's branding or proprietary assets.

Define a small, coherent set of semantic colors, text styles, spacing and shapes. Respect the existing brand, including justified multiple accents. Avoid arbitrary decorative gradients and generic cards added without a product reason. Use native semantic text styles, SF Symbols and controls where they fit. Prefer system behavior to custom recreations of navigation bars, keyboards or sheets.

Use flexible layouts; do not hardcode a screenshot's dimensions as universal device geometry. Preserve safe areas around content and primary actions.

## Build complete behavior

Read [swiftui-patterns.md](references/swiftui-patterns.md) when implementing navigation, controls, data ownership or motion.

Specify entry, exit, back, cancel, skip, validation and persistence before wiring a flow. Keep UI navigation state separate from authoritative account, onboarding and purchase state. Completing a transaction must not leave an obsolete screen reachable by Back; accessing a gated feature should return to the originating context after success.

Implement relevant loading, empty, error, success and offline states with actionable copy. Avoid duplicate submissions and navigation on rapid taps. Use optimistic updates only for reversible actions with rollback; reflect purchases and other irreversible operations from confirmed results. Use StoreKit and verified entitlements for real in-app purchases when in scope; clearly label mock purchase flows.

## Motion and assets

Keep system navigation, sheets, scrolling and control feedback native. Add custom motion only for a clear feedback or continuity purpose; scope animation to the changing state. Honor Reduce Motion and avoid animating the entire hierarchy on unrelated updates. Use haptics sparingly and never as the sole feedback channel.

Prefer SF Symbols for controls. When custom art is needed, use available user assets or supported image generation, keep one art direction and inspect edges in both themes. Package assets in the asset catalog at appropriate pixel densities or supported vector formats. Do not recreate reference watermarks, brand logos or bake interface text into images.

## Verification and finish

Read [verification.md](references/verification.md) before reporting implementation complete. Build with the project's real scheme and supported simulator; inspect rendered screens and exercise the changed flow when Xcode is available. Fix concrete defects and recheck the affected behavior. Stop when the agreed acceptance criteria are met, rather than chasing an unbounded claim of perfection.

If macOS/Xcode or interaction tooling is unavailable, complete the feasible source work and report exactly which build, visual and device checks remain. Do not replace the deliverable with a web prototype or claim simulator or device performance results that were not obtained. Previews help layout iteration but do not prove navigation or purchase behavior.

Report what changed, references used, verification performed and material remaining limitations. No automatic publication, signing-account changes or paid actions are implied by this workflow.

## Provenance

For source attribution and licensing, see [provenance.md](references/provenance.md) and LICENSE.
