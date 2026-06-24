# Gift Image Resizer Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a gift-only 800x800 image creation tool that preserves existing validation and preview flows.

**Architecture:** Keep the static single-file app. Add a compact editor panel for gift tabs, draw the adjusted result to canvas, and let users download or apply the generated image back into the current validation flow.

**Tech Stack:** HTML, CSS, vanilla JavaScript, FileReader, Image, Canvas.

---

### Task 1: Add Gift Resizer UI

**Files:**
- Modify: `index.html`

- [x] Add a hidden gift-only editor block below the upload area.
- [x] Reuse existing visual style and form controls.
- [x] Show the editor only for `gift-interest` and `gift-sheet` after an image is uploaded.

### Task 2: Add Canvas-Based Generation

**Files:**
- Modify: `index.html`

- [x] Add state for scale, x offset, y offset, generated blob, and generated data URL per gift tab.
- [x] Draw the original image into an 800x800 white canvas with preserved aspect ratio.
- [x] Update the generated preview whenever controls change.

### Task 3: Add Download and Apply

**Files:**
- Modify: `index.html`

- [x] Add PNG download for the generated 800x800 image.
- [x] Add “이 이미지로 검수하기” to convert the canvas output to a File and rerun existing validation.
- [x] Preserve existing banner behavior.

### Task 4: Add Quality Warnings

**Files:**
- Modify: `index.html`

- [x] Detect likely non-white/non-transparent backgrounds for gift images.
- [x] Detect likely edge contact or insufficient margin.
- [x] Add duplicate-product guidance as user-facing checklist/help text rather than unreliable automatic object detection.

### Task 5: Verify Manually

**Files:**
- Open: `index.html`

- [x] Test banner tab still hides the maker panel.
- [x] Test gift tab shows the maker panel before upload with the action disabled.
- [ ] Test gift-interest upload, edit, download, apply.
- [ ] Test gift-sheet upload, edit, download, apply.
- [ ] Confirm warnings render without blocking existing validation unexpectedly.
