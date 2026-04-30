# Feedback Tool — Feature Set
**Single-file HTML application for collecting structured Claude Code feedback**

---

## Core Features

### 📝 Feedback Entry
**Create detailed feedback items with multiple input methods**

- **Description** — Main issue summary (required, or screenshot needed)
- **Severity** — Low, Medium, High, Critical
- **Category Tags** — Frontend, Backend, UX, Performance, Crash
- **File Location** — Source file reference (e.g., src/components/Button.tsx)
- **URL** — Link to affected page or documentation
- **Frequency** — Always, Sometimes, Once

---

### 🖼️ Screenshots & Design References
**Attach images with automatic compression**

- **Screenshot drop zone** — Drag or click to attach issue screenshot
- **Design Reference** — Optional mockup/wireframe for UI/UX issues
- **Auto-compression** — Images optimized to 1200px width, 70% JPEG quality
- **Preview before save** — Click thumbnail to view full-size in modal
- **Delete attached image** — Remove and reattach as needed
- **Base64 storage** — Images embedded in data for offline portability

---

### 🚀 Quick Templates
**Pre-fill form with common feedback types**

Available templates:
- **UI Bug** — Visual issues, UX problems (High severity, Frontend/UX tags)
- **Performance** — Slow load, laggy interactions (High severity, Performance tag)
- **Crash** — Unhandled errors, application crashes (Critical severity, Crash tag)
- **Typo** — Spelling or grammatical errors (Low severity, Frontend tag)
- **API Issue** — Failed requests, wrong data (High severity, Backend tag)

Each template pre-fills description, severity, tags, and frequency—save time on similar issues.

---

### 💾 Auto-Save Form State
**Never lose unsaved work**

- **Debounced save** — Saves every 1 second as you type (waits for pause)
- **Browser storage** — Uses localStorage for client-side persistence
- **Auto-restore** — Form reloads with last session's draft on page open
- **Recovery message** — "📝 Recovered unsaved form data" appears on restore
- **Clear on submit** — Auto-save cleared when feedback item is added
- **Manual clear** — Clears on "Clear" button click

Saved fields: description, file location, URL, severity, steps, expected behavior, error messages, frequency, tags, and screenshot state.

---

### 🔍 Search & Filter
**Find feedback items by keyword**

- **Real-time search** — Type to filter items as you go
- **Debounced (300ms)** — Waits for typing to pause before filtering
- **Multi-field search** — Searches description, file location, and tags
- **Result count** — Shows "X items matching" or "No items found"
- **Quick clear** — Press Escape in search box to clear and reset list
- **Keyboard shortcut** — Ctrl+K / Cmd+K to focus search anytime

---

## Item Management

### 📋 View Items
**Browse feedback in organized list**

- **Item cards** — Compact view with status, number, and key details
- **Expandable rows** — Click to see full description, screenshots, metadata
- **Collapsible sections** — Hide/show entire items list with toggle
- **Drag reorder** — Reorder items by dragging (visual feedback on drag)
- **Item count** — See total items in header

Item card shows:
- Status indicator (✓ complete, ⚠ incomplete)
- Item number and sequential ID
- Description preview with line breaks preserved
- Meta info: severity tag, category tags, frequency
- Action buttons: Copy, Edit, Delete (appear on hover)
- Screenshots/design reference thumbnails

---

### ✏️ Edit Items
**Modify feedback after creation**

- **Full edit modal** — Reopens form with all fields populated
- **Edit any field** — Description, severity, tags, steps, expected behavior, error messages, design reference
- **Change screenshots** — Replace or update attached images
- **Save or cancel** — Modal buttons with clear actions
- **Validation** — Requires description or screenshot (same as creation)

---

### 🗑️ Delete Items
**Remove feedback with protection**

- **Single delete** — Delete button on each item card with confirmation
- **Batch delete** — "Delete All" button removes all items at once
- **Confirmation modal** — Shows what will be deleted before confirming
- **Undo support** — Deleted items saved in undo stack
- **Undo delete button** — Appears after deletion, restores single or batch
- **Persistent undo** — Stack saved to localStorage (survives page reload)

Workflows:
- Single delete: Click ×, confirm → item gone, "Undo delete" appears
- Batch delete: Click "Delete All", confirm with count → all cleared, "Undo delete" appears
- Undo single: Restores one item
- Undo batch: Restores all items from batch delete at once

---

### 📌 Additional Details (Expandable)
**Collapse/expand section for optional fields**

Includes:
- Steps to Reproduce
- Expected Behavior
- Error Messages / Stack Traces
- Design Reference Screenshot
- Frequency selector
- Category/Tags checkboxes

Section starts collapsed to reduce form clutter; expand when needed.

---

## Keyboard Shortcuts
**Power user productivity**

| Shortcut | Action |
|----------|--------|
| **Ctrl+Enter** | Submit feedback item |
| **Escape** | Clear form (when description focused) |
| **Ctrl+K / Cmd+K** | Focus search box |
| **Escape** (in search) | Clear search results |

Shortcuts discoverable via **? Help** button in form header.

---

## Preview & Export

### 📄 Markdown Preview
**Real-time standardized format**

Preview shows feedback rendered in standardized markdown format suitable for Claude Code:
- Structured headings (Issue, Details, Steps, Expected, Actual)
- Severity and tags prominently displayed
- Metadata organized and readable
- Auto-updates as you type

---

### 📤 Export Options

**Copy & Paste**
- Copy markdown text directly
- Paste into Claude Code chat
- Upload screenshots separately as a folder

**Download Zip**
- Complete package: markdown + all screenshots
- Single file for easy sharing
- Upload entire folder to Claude Code
- Paste markdown from extracted files

Both options format feedback in standardized structure Claude Code expects.

---

## UI/UX Polish

### 🎨 Modal Confirmations
**Styled confirmation dialogs (no browser alerts)**

Replace jarring browser `alert()` with custom modals:
- Delete confirmations show what will be deleted
- Clear, readable messaging
- Large clickable buttons
- Click outside to cancel
- Consistent styling throughout app

---

### 💬 Success Messages
**Feedback on key actions**

Auto-dismiss messages:
- "Item deleted. Click 'Undo delete' to recover."
- "Restored X items."
- "Item updated."
- "Item added. Click 'Copy Markdown' to export."

Messages appear 3 seconds then fade.

---

### 🎯 Visual Feedback
**Clear interaction states**

- **Hover effects** — Buttons, cards, form elements highlight on hover
- **Drag states** — Items show 50% opacity while dragging
- **Drag-over zone** — Blue background + border on drop target
- **Expanded sections** — Arrow rotates 180° when section opens
- **Loading animations** — Smooth transitions on all state changes

---

## Design & Performance

### 🎨 Modern Design System
**Consistent, professional appearance**

- **8px grid** — Unified spacing throughout
- **4 font sizes** — Clear visual hierarchy
- **Color palette** — Blues for primary, grays for secondary, red for danger
- **2 shadow levels** — Small for interactive, medium for elevated
- **Responsive layout** — Two-column on desktop, stacks on mobile

### ⚡ Performance Features
- **Debounced search** (300ms) — Smooth typing, no lag
- **Debounced auto-save** (1s) — Efficient storage writes
- **Image compression** — 1200px width, 70% quality
- **LocalStorage** — Fast client-side persistence, no server needed
- **Single-file app** — One HTML file, no build step, offline-capable

---

## Data Management

### 💾 LocalStorage Persistence
**Automatic backup**

- **Items saved** — Each feedback item stored as JSON
- **Form state saved** — Current form draft preserved
- **Undo stack saved** — Deletion history persists
- **Survives refresh** — Page reload doesn't lose data
- **Offline capable** — Works completely without internet

---

### 📦 Data Portability
**Export formats**

- **Markdown** — Readable text format for sharing
- **Zip package** — Complete export with all screenshots
- **Base64 embedded** — Screenshots encoded in item data
- **No vendor lock-in** — Export anytime, use anywhere

---

## Accessibility Features

**WCAG 2.1 Level AA Compliance:**
- **Keyboard navigation** — Full keyboard support for all interactive elements, including collapsible sections
- **Keyboard shortcuts** — Tab navigation, Enter/Space to activate buttons, Escape to close dialogs
- **Focus indicators** — Strong 3px blue focus outline on all interactive elements
- **Labels** — All form inputs properly associated with labels using `for` attribute
- **Color contrast** — All text meets WCAG AA 4.5:1 minimum contrast ratio
- **ARIA labels** — Comprehensive ARIA labels and descriptions for screen readers
- **ARIA expanded** — Dynamic aria-expanded states on collapsible sections
- **Semantic HTML** — Proper heading hierarchy, fieldset/legend for grouped controls, label associations
- **Screen reader support** — Full compatibility with assistive technology
- **Visual indicators** — Drag handle indicators (⋮⋮) for draggable items

---

## File Structure

Single self-contained HTML file (~2200 lines):
- **HTML** — Form, modals, items display, templates
- **CSS** — Responsive layout, animations, modern styling
- **JavaScript** — Core functionality, state management, storage
- **No dependencies** — Single external: jszip.js for zip export

---

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)
- Offline-first architecture works in all modern browsers

---

## Future Enhancements

Potential additions (not currently implemented):
- Drag-and-drop reordering persistence
- Tagging system with custom tags
- Issue templates with custom fields
- Integration with Claude Code API
- Team sharing and collaboration
- Advanced filtering (by severity, tag, date)
- Performance optimizations for 1000+ items
