# Correction prompts

These are the follow-ups used on Flowly, written from the real check results of each round. Use them as patterns: name the width, name the exact problem, say what done looks like, ask for a re-check.

## 0. Direction override (when the agent picks a direction your refs don't support)

```text
None of the three directions you dealt (quiet-instrument, split-stage,
colour-chapters) match refs/NOTES.md. Don't take any of them. Take the
direction from the references: editorial grotesk + photography. One family,
huge regular-weight wordmark over a full-bleed photo, bone and ink only.
```

## 1. Round 1 fails (layout bugs at specific widths)

```text
Round 1 has 3 FAILs. Fix all three:
1. At 768px, the captions above "48 h" and "14 days" read as labels over the
   numbers. Put each caption beside or under its own numeral.
2. At 390px, the hero statement and "Made in Barcelona. Data in Frankfurt."
   wrap to 3 lines. Cut words first; the statement is a paragraph, so set it
   as a <p> at 22px.
3. At 390px there's an 864px blank gap near the bottom. Find what's holding
   the space and close it.
Then re-run the check and re-screenshot all three widths.
```

## 2. The scroll bug

```text
Every frame of the page screenshots shows the same screen: the page never
scrolled. Lenis keeps its own target when something jumps with scrollTo, then
slides back. Sync Lenis with the real scroll position before it animates,
test a few jumps, and re-screenshot.
```

## 3. Round 2 (content hidden behind animations)

```text
On phone, the FAQ stays invisible after a jump past its trigger (blank gap).
Content must never depend on a reveal animation. On phones show everything at
once; keep the rise animation only from 641px up.
```

## 4. The taste pass (0 FAIL isn't done)

```text
0 FAIL isn't done. Put the hero next to refs/marren_mockup.jpg:
- our photo is greener than his neutral greys: regrade it to a warm stone;
- the Free plan's rows stretch to the Team column's height: fix the alignment;
- the Barcelona paragraphs sit on the busiest part of the facade: move them
  over a calmer area with a scrim.
Re-screenshot at 1440, 768 and 390.
```

