# Dark Neon Typing Demo Design

## Summary
Build a single-page demo that feels like a Framer-style motion showcase: a dark stage, one large animated typewriter line, neon accents, and a small amount of atmospheric motion. The page should feel premium and focused, with the typing interaction as the main attraction rather than a marketing layout.

## Goals
- Make the typing animation immediately obvious and visually satisfying.
- Keep the page minimal so the motion has room to breathe.
- Use a dark background with neon highlights and soft glow.
- Keep the implementation self-contained in one source file so it is easy to review and iterate.
- Support desktop and mobile without changing the core experience.

## Non-goals
- No multi-page navigation.
- No forms, authentication, data fetching, or product dashboard UI.
- No external animation library.
- No complex editor, code playground, or interactive text input.

## Chosen Direction
Use a centered demo stage with a single typewriter sentence at the visual center. The rest of the UI should be supporting atmosphere only: small status chips, soft background glows, and a minimal control to replay the sequence. This keeps the page feeling like a polished demo instead of a full app.

## Page Structure

### 1) Ambient shell
- Full-screen dark background using deep navy / charcoal tones.
- Large radial gradients or blurred shapes in neon purple, cyan, and pink.
- A very subtle grid or noise layer to keep the background from feeling flat.

### 2) Demo header
- Small label in the top-left corner to frame the experiment.
- Short supporting line near the hero area that explains the motion demo in one sentence.
- Keep text minimal so the main typed line remains dominant.

### 3) Typewriter stage
- A large sentence in the center of the page.
- A blinking caret at the end of the active text.
- The sentence should be cycled through a small set of design-focused phrases.
- Use a pause after each full sentence before deleting and moving to the next one.

### 4) Supporting status row
- One to three small chips showing the current mode, such as `typing`, `pause`, and `looping`.
- The chips should change subtly with the animation state.
- These are decorative cues, not controls.

### 5) Replay control
- A minimal replay button near the lower edge of the page.
- The button should restart the typing sequence from the first phrase.
- If the animation is already running, the button can still reset the sequence cleanly.

## Motion and Interaction Model
The animation should be driven by a simple state machine in vanilla JavaScript.

### States
- `typing`: characters are added one at a time.
- `pause`: the full sentence is visible for a short moment.
- `deleting`: characters are removed one at a time.
- `next`: the phrase index advances and the cycle begins again.

### Timing
- Typing speed: fast enough to feel responsive, but slow enough to read the reveal.
- Deleting speed: slightly faster than typing so the loop feels smooth.
- Pause duration: long enough to let the user read the full phrase before it changes.

### Phrases
Use a small set of design-centered lines such as:
- `Crafting smooth interactions`
- `Designing motion with clarity`
- `Building calm, living interfaces`

The phrases should be short enough to fit comfortably on desktop and mobile.

### Ambient Motion
- Background glows drift slowly so the page feels alive.
- The caret blinks continuously.
- Optional micro-shift on pointer movement is acceptable if it remains very subtle and does not distract from the text.

## Visual Style
- **Theme:** dark, immersive, premium.
- **Primary accent:** neon cyan or electric purple.
- **Secondary accent:** soft pink or blue used sparingly.
- **Typography:** bold, clean sans-serif for the main line; smaller supporting text should be muted and restrained.
- **Shape language:** soft rounding and blurred edges instead of hard borders.
- **Contrast:** strong enough for readability, but not harsh or purely high-contrast black-and-white.

## Accessibility and Responsiveness
- Respect `prefers-reduced-motion` by reducing or disabling the continuous animation loop and presenting a stable readable state.
- Use semantic headings and button elements.
- Ensure the main sentence wraps cleanly on small screens.
- Keep the control row and chips readable on mobile without cramping the center stage.
- Maintain usable contrast for all visible text.

## Implementation Notes
- Use a single HTML file with embedded CSS and JavaScript.
- Keep DOM structure simple: shell, header, stage, status chips, replay button.
- Manage animation with one timer loop and a small state object instead of many independent intervals.
- Avoid external dependencies so the demo remains portable.

## Acceptance Criteria
- The page opens and immediately shows a dark neon demo environment.
- The center text types itself automatically and cycles through the phrase set.
- A blinking caret and subtle glow support the motion without overpowering it.
- The replay button resets the animation cleanly.
- The page remains readable and balanced on both desktop and mobile.
- Reduced-motion users receive a calmer, still-readable version of the page.

## Verification Plan
- Check the layout at desktop width for centering, spacing, and glow balance.
- Check the mobile width for wrapping, scale, and button placement.
- Verify the typing loop does not stutter or overlap text.
- Verify the replay button restarts from the first phrase.
- Verify the reduced-motion fallback is legible and stable.
