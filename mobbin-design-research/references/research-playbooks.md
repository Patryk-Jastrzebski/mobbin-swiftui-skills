# Task-sized research playbooks

## New app or new flow

1. Translate the brief into concrete research questions: first value, personalization, permissions, paywall placement, recovery and entry/exit conditions.
2. Search screens and flows with the actual Mobbin schemas. Choose a small, relevant set of contrasting examples, based on product fit and visual evidence rather than unprovided business metrics.
3. Inspect the available sequence for each selected flow. Record missing screens; never fill gaps as facts. Note what the screen asks of the user and what value it provides.
4. Compare information hierarchy, interaction choices, step ordering and friction. State which patterns support the user's goal and which should be omitted.
5. Specify an original flow. Keep visual language coherent with the user's brand and existing app. Do not add every feature found in competitors.
6. When implementation is requested, hand the specification to swiftui-reference-design if available, with source references and unresolved assumptions. Proceed on routine design choices without adding an approval gate.

## Improve a screen

Inspect the supplied screen first; name its concrete hierarchy, readability, interaction or state problems. Search targeted alternatives. If it belongs to a flow, inspect adjacent steps where available. Compare a few strong references and specify changes to layout, copy, controls and behavior. Preserve existing successful behavior. After implementation, verify the modified screen and affected entry/exit routes.

## Flow and component research

For a component, search screens using its name plus the product context; do not invent an element taxonomy tool. Record placement, labels, selected states and accessibility implications. For a journey, use search_flows and retain returned order. A collection of isolated search results is not proof of a full flow.

Use a table when useful:

| Step | User goal | Input/action | Next state | Back/cancel | Presentation | Saved data | Evidence or proposal |
| --- | --- | --- | --- | --- | --- | --- | --- |

End with the adopted pattern and its tradeoffs. When evidence is incomplete, make a clearly labeled recommendation and identify the missing evidence. Never infer measured conversion from popularity, revenue or visual polish.
