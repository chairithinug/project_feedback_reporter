# Project: incident_reporter (Feedback Tool for Claude Code)

## What this is
A lightweight, offline HTML feedback collection tool that lets you capture UX/UI issues, bugs, and design problems with screenshots and structured details. Built to help Claude Code understand and iterate on project problems with minimal friction and token consumption.

**Why:** Standardized feedback format + auto-compression reduces token waste. **For whom:** Solo developers and small teams testing Claude Code against their projects. **Commercialization:** No — internal tool only.

## Current phase
Build (Complete) → Ready for Iteration
**Done for this phase:** 
- ✅ Working local app (single-file HTML)
- ✅ Persistent screenshot & issue storage
- ✅ Structured markdown export + zip download
- ✅ All core features implemented (templates, search, undo, tags)

## Success criteria
- ✅ Local app that takes screenshots + structured issue details
- ✅ Persistent storage (localStorage auto-save)
- ✅ Generate token-efficient markdown & zip reports for Claude Code
- ✅ Expandable UI with manageable cognitive load
- ✅ Image compression to reduce token consumption
- ✅ Search/filter and template system for quick entry

## Your role here
Default to `/quick` for practical implementation questions. Flag when the tool needs actual user testing vs. assumption-based changes.

## Domain context
- **Technical stack:** Single-file HTML + vanilla JS + localStorage + JSZip (no build, no dependencies beyond CDN)
- **User:** ML/data engineer, low business literacy, Bangkok-based
- **Target use case:** Iterating Claude Code on UX/UI problems — provide screenshot + standardized issue format

## Output conventions
- **Files:** Single `feedback-tool.html` is the tool; `.md` files are documentation
- **Code:** Vanilla JS, inline styles, self-contained (no external deps except JSZip for export)
- **Exports:** Markdown for copy-paste to Claude Code; zip bundles markdown + images

## Project safeguards (additions to global)
- Token optimization is a hard requirement — always compress images and minimize empty fields in exports
- No backend/cloud features — must stay offline-first
- Don't add complexity without user request — cognitive load matters