# Analytical Design — Extensions from Tufte's Later Work

Reference for the `tufte-viz` skill. Drawn from:
- *Envisioning Information* (1990)
- *Visual Explanations* (1997)
- *Beautiful Evidence* (2006)

---

## Six Principles of Analytical Design

From *Beautiful Evidence*, Chapter 5. These principles apply to any presentation of evidence, including data graphics.

1. **Show comparisons, contrasts, differences.** An answer is only as informative as the question it is compared against. Always show the comparison that motivated the question.

2. **Show causality, mechanism, explanation, systematic structure.** Reveal the causal processes behind the data, not just the outcomes.

3. **Show multivariate data.** The world is multivariate. Most interesting questions involve more than 2 variables. Graphics that show 3+ variables simultaneously reveal structure invisible in pairwise plots.

4. **Completely integrate words, numbers, images, diagrams.** Segregating text and graphics into separate zones (caption far from chart) forces the viewer to travel between them. Integrate them directly.

5. **Thoroughly describe the evidence.** Provide a detailed title, the source of the data, scale indicators, definitions of terms. Credibility comes from detail.

6. **Analytical presentations ultimately stand or fall depending on the quality, relevance, and integrity of their content.** Excellent design cannot rescue bad data or a bad question.

---

## Sparklines

> "A sparkline is a small intense, simple, word-sized graphic with typographic resolution."

Sparklines are data-words: inline graphics about the size and weight of a word of text, embedded in narrative.

Design rules:
- Same height as the x-height of surrounding text (~12px at body size)
- No axes, no labels, no tick marks
- Show the shape — trend, range, recent value
- End with a highlighted final point in red (or a high/low dot pair)
- Can be used in tables alongside text values

Use cases: stock prices in financial tables, patient vital signs in medical records, economic indicators in policy documents.

---

## Layering and Separation

From *Envisioning Information*, Chapter 2.

**Layering** is the use of visual variables (color, value, texture, pattern) to assign different levels of visual importance to different information layers. The goal is to place the data in the visual foreground and context in the background.

The 1+1=3 problem: when two adjacent elements share the same visual weight, the interface between them becomes a third element — visual noise. Use contrast to keep elements separated.

**Separation techniques:**
- Vary line weight (thin for reference, thick for data)
- Use color value (light gray for background grid, black for data)
- Use transparency to show context without obscuring data
- Place annotations in clear space, away from data

The magic of layering: a good background/foreground distinction can increase the effective information density of a graphic without increasing visual clutter.

---

## Micro/Macro Design

From *Envisioning Information*, Chapter 2.

A well-designed graphic works at multiple scales simultaneously:
- **Macro**: overall pattern, trend, shape visible at a glance
- **Micro**: individual data points readable on close inspection

These two levels should reinforce each other. The macro pattern guides the eye to interesting regions; the micro detail rewards closer inspection.

Practical implication: do not aggregate away the raw data to show only summary statistics. Show dots + running median simultaneously. The dots are the micro layer; the median line is the macro layer.

---

## Escaping Flatland

From *Envisioning Information*, Chapter 1.

Information is inherently multivariate — it exists in n-dimensional space. The printed page (and screen) is flat — 2-D. The challenge is to escape flatland by encoding additional dimensions into the 2-D surface.

Techniques:
- **Small multiples**: add a third dimension by replicating the 2-D graphic across a panel grid
- **Color/value**: encode a third variable as the color or gray value of points
- **Size**: encode magnitude as circle area (with care — area is harder to judge than length)
- **Layering**: use foreground/background to suggest depth
- **Narrative sequence**: use animation or multiple frames to show change over time

The most powerful escape from flatland is small multiples: each panel is a 2-D display, but the comparison across panels adds a third (or fourth) dimension.

---

## Range-Frame and Dot-Dash Plot

From *The Visual Display of Quantitative Information*, Chapter 6 (introduced here as a reference because it extends data-ink principles).

### Range-Frame
Replace the conventional chart box (four lines enclosing the plot area) with two lines that span only the range of the data:
- x-axis line: from minimum x to maximum x
- y-axis line: from minimum y to maximum y

This transforms the axis into a two-sided one-dimensional representation of the data range, eliminating the visual frame while conveying more information.

### Dot-Dash Plot (Rug Plot)
Add marginal tick marks to a scatter plot — one tick per observation on each axis. This adds:
- A one-dimensional scatter of the x marginal distribution (on the x-axis)
- A one-dimensional scatter of the y marginal distribution (on the y-axis)

At no additional area cost, you get marginal distributions for free.

---

## Confections, Parallelism, and Narrative

From *Visual Explanations*, Chapter 4.

**Confections** are composite graphics that combine multiple images to tell a story. They work through parallelism — showing the same thing at different times, scales, or conditions.

Design principles for confections:
- Establish a consistent orientation (up is always north, or up is always "more")
- Align comparable elements across panels
- Use consistent scale unless the point is the scale difference
- Allow the eye to travel across panels — don't force it to re-orient

**Narrative** graphics show causality through sequence — before/after, cause/effect, input/output. Always make the direction of time or causation explicit with arrows or sequence labels.

---

## Cause and Effect

> "Confusion between correlation and causation is the most common error in statistical graphics."

For graphics that claim to show causal relationships:

1. Show the cause and effect in the same graphic
2. Show the mechanism connecting them
3. Show the counterfactual (what would have happened without the cause)
4. Show dose-response if available (more cause → more effect)
5. Address alternative explanations in the caption

The classic failure: showing a single time series labeled "X caused Y" with no counterfactual and no mechanism. Always ask: "compared to what?"
