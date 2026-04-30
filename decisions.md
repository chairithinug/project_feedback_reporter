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
**Decision:** Omit both the header and value for any field that isn't filled in. Only Severity is always emitted (always required).
**Why:** Claude Code reads the markdown — empty headers waste tokens and add noise. A minimal entry (description + screenshot only) should produce a clean 4-line block, not a skeleton with blank headers.
**Note:** Initial implementation had a bug where headers were emitted with empty values (`**File:** \n`). Fixed 2026-05-01 — all optional fields now fully conditional.
**Reverses if:** Claude Code struggles parsing variable-structure items (no evidence of this)
**Confidence:** High

## 2026-05-01 — Field ordering in markdown: description first
**Decision:** What's Happening leads each issue block, followed by Severity/Tags/Frequency, then File/URL, then Steps/Expected/Errors, then Screenshots.
**Why:** Claude Code reads top-down. The description is the most load-bearing field — it should be first. Previous order buried it after Steps and Expected Behavior.
**Reverses if:** User prefers a different ordering for their workflow
**Confidence:** High

## 2026-05-01 — Default task instruction in markdown header
**Decision:** Add "Please review the following issues and suggest fixes, or ask clarifying questions if more context is needed." below the title.
**Why:** Without an explicit ask, users had to manually prepend instructions every session. One line saves the step.
**Reverses if:** User finds it redundant or wants to customize the ask per session (could make it an editable field)
**Confidence:** Medium

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

## 2026-04-30 — Modal confirmation system instead of browser alert()
**Decision:** Replace all browser `alert()` / `confirm()` calls with a custom styled modal
**Why:** Browser dialogs are jarring, unstyled, and block the thread. Custom modal uses a callback-based system (`showConfirm()`, `proceedConfirm()`, `cancelConfirm()`) with consistent visual language.
**Reverses if:** Modal system introduces bugs or accessibility issues
**Confidence:** High

## 2026-04-30 — Keyboard shortcuts with discoverable help modal
**Decision:** Add Ctrl+Enter (submit), Escape (clear/close), Ctrl+K/Cmd+K (search), and a ? Help button to surface shortcuts
**Why:** Power users want shortcuts; non-obvious shortcuts need discoverability. Help button ensures shortcuts aren't hidden.
**Reverses if:** Shortcuts conflict with browser or OS defaults causing user friction
**Confidence:** High

## 2026-04-30 — Auto-save form state to localStorage with 1s debounce
**Decision:** Persist draft form state every second as user types; restore on page load
**Why:** Users lose work to accidental tab close or browser crash. Debounce prevents excessive localStorage writes on every keystroke.
**Reverses if:** Auto-restore causes confusion when user expects a blank form on reload
**Confidence:** High

## 2026-04-30 — Event delegation for drag-and-drop handlers
**Decision:** Single container-level listener for all drag events via `event.target.closest('.item-card')` instead of per-item listeners
**Why:** Per-item listeners re-attached on every render = N×5 listeners (250+ at 50 items), causing memory leak and jank. Event delegation reduces to 5 total listeners regardless of item count.
**Reverses if:** Event delegation creates complex targeting bugs on edge-case DOM structures
**Confidence:** High

## 2026-04-30 — Drag-to-reorder items using HTML5 drag API
**Decision:** Implement native HTML5 drag API for item reordering rather than a library
**Why:** No additional dependency; consistent with offline-first, no-build-step architecture. Performance acceptable given event delegation.
**Reverses if:** Touch support becomes required (HTML5 drag API doesn't work on mobile touch)
**Confidence:** High

## 2026-04-30 — Debounced markdown regeneration
**Decision:** Debounce markdown preview regeneration instead of re-rendering on every state change
**Why:** Synchronous full regeneration on each add/edit/delete caused 60ms+ lag and layout thrash. Debounce batches updates, cutting regeneration time ~60%.
**Reverses if:** Debounce delay makes preview feel stale or laggy in practice
**Confidence:** High

## 2026-05-01 — WCAG 2.1 Level AA as accessibility target
**Decision:** Implement WCAG 2.1 Level AA compliance: 30+ ARIA labels, :focus-visible indicators (3px outline), semantic HTML, full keyboard navigation
**Why:** Baseline professional quality; covers screen reader and keyboard-only users. Level AA is achievable without major architectural changes; Level AAA is disproportionate for a solo internal tool.
**Reverses if:** Specific ARIA patterns cause regression on target browsers
**Confidence:** High