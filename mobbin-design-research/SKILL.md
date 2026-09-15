---
name: mobbin-design-research
description: Research real iOS screens, components and user flows through Mobbin MCP, then turn visual evidence into an original app or screen specification for SwiftUI. Use for Mobbin-based inspiration, onboarding and paywall research, and reference-driven flow specifications.
---
# Mobbin Design Research

Use Mobbin as the reference provider and turn inspected evidence into a design specification. For implementation, use swiftui-reference-design if available; otherwise hand off a SwiftUI-ready specification.

## Establish the task

Use the user's product, audience, brand, existing design system and requested deliverable. Default the implementation target to native iOS/SwiftUI. Inspect an existing project's deployment target before recommending version-specific APIs. Do not expand a request for a flow specification into building an app.

Start from references the user supplied. For a redesign, inspect the current screen or screenshot and identify concrete problems before searching. Preserve the user's chosen product scope.

## Access and evidence

Discover the live Mobbin tools and read their schemas before calling them. Names may be connector-prefixed. The documented capability families are:

| Intent | Mobbin capability |
| --- | --- |
| Screens, visual styles, components | search_screens |
| Multi-step journeys | search_flows |
| Website sections, only when relevant | search_sections |

These are capability names, not invented call signatures. Use only exposed parameters and returned pagination mechanisms. Do not assume undocumented modes, cursors, IDs, credits, quotas, media expiry, boards, revenue filters or retrieval tools. Do not assume a complete app traversal, downloadable assets or video access exists. Re-query only through supported tools if a reference becomes unavailable.

If tools are missing, check available integration discovery and offer Mobbin when supported. Continue from attached screenshots or available evidence. Clearly label unsupported conclusions; do not pretend a public Mobbin URL alone reveals its screens. Do not switch reference providers without the user's agreement.

Inspect the actual returned images, not just labels or metadata. Record the app, platform, source link/ID when returned, observed order and what was visually inspected. Mark motion, gesture, hidden state and ordering as unknown unless supported by sequence metadata or actual video. Do not equate pixels with points without scale information. Treat inferred dimensions as estimates and choose native SwiftUI sizing deliberately.

## Research to specification

Read [research-playbooks.md](references/research-playbooks.md) for a new app, redesign or flow study.

Use focused queries covering the user's function and visual intent. Prefer iOS references; translate other platforms explicitly. Compare enough relevant alternatives to resolve the design question, then stop when more references no longer change the proposed design. Avoid fixed screenshot quotas and catalog harvesting.

Produce a compact evidence-based synthesis: adopted pattern, reason it fits, adaptation to this product, and unresolved uncertainty. References establish conventions and alternatives; they do not establish conversion, retention or business outcomes.

For a flow, specify each screen's purpose, input, primary action, secondary/skip action, validation, next state, back/cancel behavior, presentation and persistence. Include loading, empty, error and relevant offline states. Separate observed reference behavior from proposed behavior. Translate into NavigationStack, tabs or modal presentations only after reasoning about the task.

Use the user's language for the handoff. Include reference links next to findings when available. Save research files only when useful to implementation; keep credentials and signed media URLs out of durable notes. End a research-only task with the specification; proceed to implementation only when requested.

## Provenance

For source attribution and licensing, see [provenance.md](references/provenance.md) and LICENSE.
