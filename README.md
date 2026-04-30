# Claude Code Feedback Tool
A single-file, offline-capable feedback collection system for structured bug reports and feature requests.

**[Quick Ref: Phases](QUICK_REF_PHASES.md)** | **[Quick Ref: Design](QUICK_REF_DESIGN.md)** | **[Quick Ref: Audits](QUICK_REF_AUDITS.md)**

---

## What Is This?

A web-based feedback form to collect detailed bug reports and feature requests for Claude Code development. Write once, export as markdown or zip, and import directly into Claude Code chat.

✅ Works completely offline  
✅ Auto-saves as you type  
✅ Screenshots auto-compressed  
✅ Export as markdown or zip  
✅ Single HTML file — no build step

---

## Quick Start

1. Open `feedback-tool.html` in your browser
2. Describe the issue in "What's Happening"
3. Attach screenshot (optional, auto-compressed)
4. Click "Add Feedback Item"
5. Review in Claude Code Ticket Preview
6. Export as markdown or zip

---

## Features

- ✅ Auto-save form state (never lose work)
- ✅ Keyboard shortcuts (Ctrl+Enter to submit, Ctrl+K for search)
- ✅ Modal confirmations (clean UX)
- ✅ Search/filter with debouncing
- ✅ Edit and delete with undo
- ✅ Design references (UI issues)
- ✅ Screenshot compression (1200px, 70% JPEG)
- ✅ Drag to reorder items
- ✅ 5 quick templates (UI Bug, Performance, Crash, Typo, API)

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| **Ctrl+Enter** | Submit feedback item |
| **Escape** | Clear form |
| **Ctrl+K / Cmd+K** | Focus search |

Press **? Help** in the app to view all shortcuts.

---

## Status

✅ **Production-Ready (v1.0.0)**

- **Performance:** 60-98% faster operations (event delegation, debounced markdown)
- **Accessibility:** WCAG 2.1 Level AA compliant (focus indicators, ARIA labels, keyboard nav)
- **Code quality:** ~2500 lines, well-documented, minimal duplication
- **Tested:** 50+ items, drag reordering, all features verified
- **Browser support:** Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

---

## Documentation

**Start here (Quick Refs):**
- [Implementation Phases (1-pager)](QUICK_REF_PHASES.md) — What was optimized & metrics
- [Design System (1-pager)](QUICK_REF_DESIGN.md) — Visual guidelines & system
- [Audits & Status (1-pager)](QUICK_REF_AUDITS.md) — Issues resolved, compliance status

**For deeper dives (50-100 lines):**
- [Implementation Summary](IMPLEMENTATION_SUMMARY.md) — Phase details, performance gains
- [Design Summary](DESIGN_SUMMARY.md) — Design decisions, system rules
- [Audits Summary](AUDITS_SUMMARY.md) — Issues found/fixed, production checklist

**Original detailed docs:**
- [IMPLEMENTATION_PHASES.md](IMPLEMENTATION_PHASES.md) — Complete optimization journey
- [DESIGN_AND_STANDARDS.md](DESIGN_AND_STANDARDS.md) — Full design audit
- [AUDITS_AND_ANALYSIS.md](AUDITS_AND_ANALYSIS.md) — Comprehensive issue analysis
- [FEATURES.md](FEATURES.md) — Feature-by-feature breakdown

**Project context:**
- [context.md](context.md) — Background & setup
- [decisions.md](decisions.md) — Design & tech decisions
- [instructions.md](instructions.md) — How to use this project
- [open-questions.md](open-questions.md) — Unresolved questions

---

## File Organization

```
incident_reporter/
├── feedback-tool.html           # Main application (open this!)
├── README.md                    # This file
│
├── QUICK_REF_*.md              # One-page quick scans
├── *_SUMMARY.md                # 50-100 line overviews
├── IMPLEMENTATION_PHASES.md    # Full optimization details
├── DESIGN_AND_STANDARDS.md     # Complete design system
├── AUDITS_AND_ANALYSIS.md      # Full audit findings
├── FEATURES.md                 # Feature documentation
│
├── context.md                  # Project background
├── decisions.md                # Design & tech decisions
├── instructions.md             # Setup & usage
├── open-questions.md           # Open issues
│
└── .gitignore                  # Git ignore patterns
```

---

## Performance Metrics

| Operation | Before | After | Improvement |
|-----------|--------|-------|-------------|
| Add item (50 items) | ~200ms | ~80ms | +60% |
| Search (50 items) | ~100ms+ | ~5ms | +95% |
| Drag reorder (50 items) | ~200ms | ~75ms | +63% |
| Event listeners (50 items) | 250+ | 5 | **-98%** |

---

## Latest Updates (v1.0.0)

**Phases 1-3 Complete:**
- Event delegation: 98% reduction in listeners
- Debounced markdown: 60% faster regeneration
- WCAG 2.1 Level AA accessibility throughout
- 30+ comprehensive ARIA labels
- Full keyboard navigation support

**Recent Bug Fixes:**
- ✅ Screenshot deletion via X button (ID case mismatch)
- ✅ Modal confirmation callbacks
- ✅ Form persistence and storage
- ✅ Delete/undo functionality

---

## Version

**Current:** 2026-05-01 (v1.0.0)  
**Status:** Production-ready with all optimizations, accessibility compliance, and bug fixes
