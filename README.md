# Retro-retro-tool

A simple game to track weekly team retro ratings (1–5). A line moves week to week; consecutive ups or high scores make it glow with confetti and fireworks, drops trigger a 😢 rain. Team members are added by initials, rated via input/dropdown, and can upload a photo that appears on an animated stick figure with swinging limbs that floats at its last position between updates. State persists between runs, restartable, and repopulatable via a simple matrix. Required: responsive full-screen canvas, touch-only controls, a start screen, and an internal QA pass before delivery.

<img width="541" height="640" alt="image" src="https://github.com/user-attachments/assets/1b4e36b3-8bbb-42b3-910a-f011cacd85d2" />


**v1 — First build**
Core loop shipped: single team-average line, confetti/fireworks on streaks, crying rain on drops, add-member-by-initials, photo upload onto a stick figure, save/load via storage, start screen, matrix repopulation, touch-drag panning.

**v2 — UX labeling + bug fixes** (from your annotated screenshot)
Restructured the panel into three explained rows (members / add member / rate). Added **per-member coloured lines** instead of one shared line (while average still drove effects at this stage). Fixed the photo-not-showing-on-figure bug, added a colour picker per member, and made the stickman cuter and rounder per your note.

**v3 — Dropped team average, added emoji identity**
Removed the average line entirely — each member's own line now independently triggers its own confetti/fireworks/rain based on *their* week-over-week change. Replaced photo upload with a 24-emoji picker (faces, animals, fun icons) for each member's stick-figure face, removing the photo-size storage concern.

**v4 — Focus mode + smarter week handling**
Added tap-to-focus: selecting a member (via chip or dropdown) highlights their line and dims others. Fixed the week box so it no longer jumps forward immediately after you submit a rating. Made selecting a member auto-fill the week box to their next un-rated week (gap-aware).

**v5 — Spacing, view modes, export, sound, sprint-week variable**
Widened top/side margins so figures don't clip. Added a 👁 view-mode cycle (Spotlight/Solo/All) plus point-jitter so overlapping scores are readable with a big team. Added matrix **export** (colours + emojis + ratings, blanks for missed weeks). Added randomized celebration/sad emoji showers with synthesized "hooray" and "cry" sounds (with mute toggle). Added an editable **Sprint Week** variable so members who missed a retro get pre-filled to the current sprint week instead of their own last gap.

**v6 — Fixed the blank-screen load failure + team mood**
Root-caused the blank screen: the whole layout used `position:fixed`, giving the document zero intrinsic height in the app's auto-sizing view — collapsed to nothing. Rebuilt as an in-flow flex layout with a hard minimum height and self-healing canvas sizing. Added an on-screen error banner for any future runtime failure. Added the **team mood row** — one averaged emoji (🤩😄🙂😕😭) per week under the chart.

**v7 — Export moved in-game**
Relocated Export from the start screen to a floating **⇪ Export** button in the top-right corner of the live game, opening a bottom sheet with the copyable/exportable matrix — so you can pull ratings mid-session without returning to the menu.
