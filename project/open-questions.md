# Open Questions

## Unresolved


- **Q:** Is image compression (max 1200px, 70% JPEG) sufficient, or do users need lossless export option?
  - **Why it matters:** Token optimization vs. visual fidelity trade-off. Compression helps unless users need pixel-perfect screenshots.
  - **What would resolve it:** Gather feedback after real use — does Claude Code need higher quality? Do users want lossless option?
  - **Owner:** User — observe during actual workflow


## Closed

- **Q:** Should the tool be single-file HTML or a multi-file project? → **Resolved 2026-04-30:** Single-file HTML chosen for zero build step, offline-first, and easy sharing. No framework complexity needed.

- **Q:** Should empty fields appear in the exported markdown? → **Resolved 2026-04-30:** No — omit placeholder text to optimize tokens. Field headers always present but values blank if not filled.

- **Q:** What image compression is appropriate? → **Resolved 2026-04-30:** Max 1200px width, 70% JPEG quality. Reduces payload ~70-80% without visible loss for UI screenshots. Can revisit if Claude Code needs higher quality.

- **Q:** Does the markdown export format work well for Claude Code? → **Resolved 2026-05-01:** Audited and fixed. Three issues found: empty fields weren't omitted (bug), field order buried the description, and no default task instruction. All three corrected in `generateMarkdown()`.

- **Q:** Should design reference screenshots be supported? → **Resolved 2026-04-30:** Yes. Added as optional field in Additional Details. Displays alongside problem screenshots in expandable item cards.

- **Q:** Should the tool support drag-and-drop reordering of items? → **Resolved 2026-04-30:** Yes. Implemented via HTML5 drag API with event delegation. Verified working with 50+ items.

- **Q:** How should the UI handle many feedback items without becoming overwhelming? → **Resolved 2026-04-30:** Implemented expandable item cards with collapsible details, search/filter, tags, and thumbnail previews. Reduces cognitive load while keeping details accessible.

- **Q:** Should the tool have undo functionality for deleted items? → **Resolved 2026-04-30:** Yes. Implemented undo stack with visible "Undo delete" button. Reduces user anxiety around data loss.