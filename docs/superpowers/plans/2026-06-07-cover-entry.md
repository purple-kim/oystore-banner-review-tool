# Cover Entry Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a Notion-like cover page that lets users choose between the existing 올영매장 tool and a clickable 올리브베러 placeholder.

**Architecture:** Keep the static single-file app. Add a lightweight app screen state that toggles between the cover page, existing 올영매장 tool, and an empty 올리브베러 page without changing the current validation logic.

**Tech Stack:** HTML, CSS, vanilla JavaScript.

---

### Task 1: Add Cover And Placeholder Markup

**Files:**
- Modify: `index.html`

- [x] Add a `cover-page` section before the existing app container.
- [x] Wrap the existing app UI in an `oy-tool-page` section so it can be hidden until selected.
- [x] Add an `olivebetter-page` section with a title and empty tool area.
- [x] Add return-to-cover buttons for service pages.

### Task 2: Add Cover Page Styling And Card States

**Files:**
- Modify: `index.html`

- [x] Add Notion-like page layout styles: white background, wide content column, large title, simple copy, two-column cards.
- [x] Add service card default state.
- [x] Add service card hover state with darker border, slight lift, and subtle shadow.
- [x] Add service card pressed state with reduced lift.
- [x] Add selected state using understated border/background treatment.
- [x] Add mobile single-column layout.

### Task 3: Add Screen Navigation State

**Files:**
- Modify: `index.html`

- [x] Add `currentScreen` state with `cover`, `oy-store`, and `olivebetter`.
- [x] Add `showScreen(screenName)` to toggle visible page sections.
- [x] Add selected card tracking for the last selected service.
- [x] Ensure the initial state shows the cover page.
- [x] Keep existing tab state and validation behavior intact inside the 올영매장 tool.

### Task 4: Verify Manually

**Files:**
- Open: `index.html`

- [x] Confirm first load shows the cover page.
- [x] Confirm 올영매장 card opens the existing review tool.
- [x] Confirm existing 올영매장 tabs still work.
- [x] Confirm 올리브베러 card opens the placeholder page.
- [x] Confirm return-to-cover works from both service pages.
- [x] Confirm hover, pressed, and selected states are visible.
- [x] Confirm desktop and mobile layouts do not overlap.
