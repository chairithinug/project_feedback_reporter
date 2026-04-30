# Context

## Background
Claude Code can help iterate on UX/UI problems, but it needs structured input: screenshots + detailed issue description in a standardized format. Manual reporting is tedious and loses context. This tool streamlines feedback collection into a single local app that generates token-efficient reports Claude Code can consume without wasted API calls on empty fields or placeholder text. Built for iterating on project problems faster.

## Prior work
**Conversation history:** Built complete feedback tool over multiple sessions with iterative feature additions:
- Initial scaffolding: core HTML structure, drop zones, localStorage persistence
- Feature additions: templates, search, tags, frequency indicators, undo stack
- Export features: markdown generation, zip download with embedded images
- UX refinement: collapsible sections, thumbnail screenshots, expandable details, better spacing
- Final layout: redesigned item cards with improved visual hierarchy

**No failed attempts** — features added were validated before implementation.

## Source material
- **Feedback-tool.html:** The complete, working tool (1923 lines)
- **Conversation transcript:** Full context available if needed

## Constraints
- **Technical:** Single-file HTML only — no build step, no backend, offline-first
- **Token efficiency:** Images must be compressed; exports must omit empty fields
- **Timeline:** Tool is complete and ready to use
- **Personal capacity:** Solo developer working part-time on this

## Stakeholders
Solo project (you). No external approval needed for changes.