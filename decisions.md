# Decisions

Append to the bottom as decisions are made. Don't edit past entries — add a new entry that supersedes if needed.

## 2026-04-30 — Single-file HTML architecture
**Decision:** Build as single self-contained HTML file instead of multi-file project or web framework
**Why:** Zero build step, no dependencies to manage, instant local execution, easy to share. Considered React/Vue but offline-first + token optimization matter more than framework features.
**Reverses if:** Feature complexity exceeds ~2000 lines or build step becomes unavoidable
**Confidence:** High

## 2026-04-30 — localStorage for persistence instead of IndexedDB or backend
**Decision:** Use browser localStorage for all state (items, screenshots as base64)
**Why:** Simpler API, sufficient for single-user tool, no backend complexity. IndexedDB overkill; backend breaks offline-first.
**Reverses if:** User needs cross-device sync or data exceeds localStorage limits (~5-10MB)
**Confidence:** High

## 2026-04-30 — Image compression on client-side before storage
**Decision:** Resize to max 1200px width, JPEG 70% quality before storing
**Why:** Token efficiency is hard requirement. Reduces payload ~70-80% without visible loss for UI screenshots.
**Reverses if:** User needs pixel-perfect screenshots or compression creates visible artifacts
**Confidence:** High

## 2026-04-30 — Omit empty fields in markdown exports
**Decision:** Don't show placeholder text like "(not specified)" for empty fields
**Why:** Claude Code reads the markdown — empty fields waste tokens. Headers always present but values blank if not filled.
**Reverses if:** Claude Code struggles parsing inconsistent formats
**Confidence:** High

## 2026-04-30 — Template system with 5 presets
**Decision:** Include UI Bug, Performance, Crash, Typo, API Issue templates
**Why:** Reduces data entry friction; covers common issue types user mentioned. Not rigid — templates prefill but user can override.
**Reverses if:** User finds templates limiting or irrelevant to actual workflows
**Confidence:** Medium

## 2026-04-30 — Expandable item cards with collapsible details
**Decision:** Show summary + thumbnail screenshots by default; details expand on demand
**Why:** Reduces cognitive load when viewing many items. Expandable sections keep main view clean while details accessible.
**Reverses if:** User prefers flat list or encounters layout issues with many items
**Confidence:** Medium

## 2026-04-30 — Export as both markdown + zip options
**Decision:** Offer two export paths: copy markdown (simple) or download zip (complete with images)
**Why:** Flexibility. Simple path for quick Claude Code conversation; zip for archival. User can choose based on use case.
**Reverses if:** One export path proves unused or confusing
**Confidence:** High