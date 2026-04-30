# Open Questions

## Unresolved

- **Q:** Does the markdown export format work well for Claude Code, or should structure be adjusted?
  - **Why it matters:** If Claude Code struggles parsing the format, token efficiency gains are lost
  - **What would resolve it:** Test with Claude Code on real feedback items; adjust format based on feedback
  - **Owner:** User — needs real-world testing with Claude Code

- **Q:** Is image compression (max 1200px, 70% JPEG) sufficient, or do users need lossless export option?
  - **Why it matters:** Token optimization vs. visual fidelity trade-off. Compression helps unless users need pixel-perfect screenshots.
  - **What would resolve it:** Gather feedback after real use — does Claude Code need higher quality? Do users want lossless option?
  - **Owner:** User — observe during actual workflow

- **Q:** Should the tool support drag-and-drop reordering of items for priority management?
  - **Why it matters:** Could improve organization for teams with many feedback items
  - **What would resolve it:** User request or observation of friction when items exceed ~20 entries
  - **Owner:** Unassigned — low priority unless user asks

## Closed

- **Q:** Should the tool be single-file HTML or a multi-file project? → **Resolved 2026-04-30:** Single-file HTML chosen for zero build step, offline-first, and easy sharing. No framework complexity needed.

- **Q:** Should empty fields appear in the exported markdown? → **Resolved 2026-04-30:** No — omit placeholder text to optimize tokens. Field headers always present but values blank if not filled.

- **Q:** What image compression is appropriate? → **Resolved 2026-04-30:** Max 1200px width, 70% JPEG quality. Reduces payload ~70-80% without visible loss for UI screenshots. Can revisit if Claude Code needs higher quality.

- **Q:** Should design reference screenshots be supported? → **Resolved 2026-04-30:** Yes. Added as optional field in Additional Details. Displays alongside problem screenshots in expandable item cards.

- **Q:** How should the UI handle many feedback items without becoming overwhelming? → **Resolved 2026-04-30:** Implemented expandable item cards with collapsible details, search/filter, tags, and thumbnail previews. Reduces cognitive load while keeping details accessible.

- **Q:** Should the tool have undo functionality for deleted items? → **Resolved 2026-04-30:** Yes. Implemented undo stack with visible "Undo delete" button. Reduces user anxiety around data loss.