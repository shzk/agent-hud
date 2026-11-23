# HUD and menu-bar window placement

The fork owns this plan. The task contract is the owner's November 23 request to configure HUD placement across displays and to make the menu-bar window movable and reliably open below the menu bar. Upstream baseline is `e3bdc8f35b274b7e06a621d9d51142ffb5fb1191`. See [HUD specification](../SPEC.md) and [menu-bar implementation decision](../DECISIONS.md). The development board had no matching existing task and had one In Progress item.

1. Extend the existing settings and HUD panel. Let the user select the primary or a named connected display and any corner. Preserve manual positioning and migrate existing coordinates when their display is available. Verify fallback and restoration as displays come and go, using stable display identity and visible screen geometry.
2. Keep the status item and its SwiftUI controls. Use a movable panel, anchored below the clicked status item on its display. Save dragged offsets per display, offer a reset, and constrain the panel to the usable area. Verify open, drag, reopen, dismissal, and bounds with normal and vertically offset/negative display geometry.
3. Run the Swift tests, synthetic application UI checks, and review the resulting branch diff. Report any display hardware scenarios left unverified. Publish changes to the owner fork within authorized access.

The scope is window placement, persistence and related UI. Agent hooks, approvals, packaging installation, upstream submissions and releases are out of scope. Stop before a merge if required verification is unavailable. Physical multi-display acceptance remains open if the test host lacks multiple displays.
