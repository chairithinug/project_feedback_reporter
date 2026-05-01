# Context

## Background
Claude Code can help iterate on UX/UI problems, but it needs structured input: screenshots + detailed issue description in a standardized format. Manual reporting is tedious and loses context. This tool streamlines feedback collection into a single local app that generates token-efficient reports Claude Code can consume without wasted API calls on empty fields or placeholder text. Built for iterating on project problems faster.

## Prior work
**Conversation history:** Built and optimized over multiple sessions across three phases:

*Phase 0 — Initial build (2026-04-30):*
- Core HTML structure, drop zones, localStorage persistence
- Templates, search, tags, frequency indicators, undo stack
- Markdown generation, zip download with embedded images
- Collapsible sections, thumbnail screenshots, expandable details, improved visual hierarchy

*Phase 1 — UX friction fixes (2026-04-30):*
- Modal confirmation system (replaced browser `alert()`)
- Keyboard shortcuts: Ctrl+Enter submit, Escape clear, Ctrl+K search, ? Help modal
- Auto-save form state with 1s debounce and auto-restore on page load
- Form validation with inline error messages
- Search debounce at 300ms

*Phase 2 — Performance optimizations (2026-04-30):*
- Event delegation: replaced per-item drag listeners with 5 container listeners (98% reduction, eliminates memory leak)
- Debounced markdown regeneration (60% faster, prevents layout thrash)
- Drag-to-reorder items with HTML5 drag API

*Phase 3 — Accessibility (2026-05-01):*
- WCAG 2.1 Level AA compliance: 30+ ARIA labels, keyboard navigation throughout
- Strong focus indicators (:focus-visible with 3px outline)
- Semantic HTML and screen-reader-friendly structure

**No failed attempts** — features added were validated before implementation.

## Source material
- **Feedback-tool.html:** The complete, working tool (2530 lines as of 2026-05-01)
- **README.md + supporting docs:** Full feature, design, audit, and implementation documentation in workspace

## Constraints
- **Technical:** Single-file HTML only — no build step, no backend, offline-first
- **Token efficiency:** Images must be compressed; exports must omit empty fields
- **Timeline:** Tool is complete and ready to use
- **Personal capacity:** Solo developer working part-time on this

## Stakeholders
Solo project (you). No external approval needed for changes.