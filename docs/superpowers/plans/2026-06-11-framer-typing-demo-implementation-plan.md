# Dark Neon Typing Demo Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Transform the current single-file page into a Framer-style dark neon demo where a large design-focused sentence types itself in the center, blinks with a caret, loops through a short phrase set, and can be replayed with one button.

**Architecture:** Keep the implementation intentionally small and self-contained in one `index.html` file. The page will use a simple layered layout, a centered typing stage, small state chips, and a lightweight JavaScript state machine to drive typing, pausing, deleting, and replaying.

**Tech Stack:** Plain HTML, CSS, and vanilla JavaScript.

---

### Task 1: Replace the existing water-themed composition with the new demo shell

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Inspect the current document structure and isolate what should be removed**

The present page is a water-themed canvas experience with large decorative words, a top bar, and a panel layout. Remove or replace those sections so the page is no longer read as an illustration or product landing page.

- [ ] **Step 2: Rewrite the HTML into a minimal demo layout**

Build a centered stage with a small label/header, one large typewriter sentence, a row of status chips, and a replay button. Keep the DOM flat and readable so the animation logic is easy to follow.

- [ ] **Step 3: Replace the visual system in CSS**

Introduce a dark background with neon glows, soft blurred shapes, rounded containers, and premium typography. Make sure the center sentence remains the visual focus at all sizes.

- [ ] **Step 4: Add the reduced-motion fallback in the stylesheet**

Ensure the page remains legible and stable when motion is reduced, with the caret and continuous movement softened or removed.

### Task 2: Build the typing animation and replay behavior in vanilla JavaScript

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Create a small animation state machine**

Implement the sequence with explicit states for typing, pause, deleting, and advancing to the next phrase. Keep timing in one place so the loop is easy to tune.

- [ ] **Step 2: Define the phrase set and typewriter behavior**

Use the approved design-focused phrases and reveal them one character at a time. After each full phrase, pause briefly, delete it, and continue to the next phrase.

- [ ] **Step 3: Wire the replay button to reset the sequence**

Make the button restart from the first phrase cleanly, even if the animation is already in progress.

- [ ] **Step 4: Update the status chips as the state changes**

Reflect the current animation mode so the surrounding UI feels alive without distracting from the main typing line.

### Task 3: Add subtle atmosphere without competing with the typing demo

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add a soft glow or ambient motion layer**

Use gradients, blur, and slow drift to create a Framer-like mood while keeping the layout simple.

- [ ] **Step 2: Keep the caret blinking and the main line visually balanced**

Make sure the caret feels natural and the text stays centered and readable during the full loop.

- [ ] **Step 3: Avoid extra UI noise**

Do not add navigation, forms, or unnecessary panels. The demo should stay focused on the typing effect.

### Task 4: Verify desktop and mobile behavior

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Check the desktop composition**

Confirm the main sentence is dominant, the chips do not crowd the stage, and the neon atmosphere feels premium rather than busy.

- [ ] **Step 2: Check the mobile composition**

Confirm the sentence wraps cleanly, the spacing remains comfortable, and the replay control stays easy to tap.

- [ ] **Step 3: Verify replay and loop stability**

Confirm the text does not overlap, the sequence resets cleanly, and the state machine continues to cycle without glitches.

- [ ] **Step 4: Verify reduced-motion behavior**

Confirm users with reduced-motion preferences still get a readable, polished page with minimal or no looping motion.

### Task 5: Save and review the final source state

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Keep the final implementation contained to one file**

Do not split the demo into additional assets unless absolutely necessary.

- [ ] **Step 2: Review the final markup, CSS, and script for clarity**

Make sure the structure remains easy to maintain and the animation code is easy to understand on a quick read.

- [ ] **Step 3: Prepare the source for handoff**

Leave the page in a state where it can be opened locally and immediately demonstrates the intended typing experience.
