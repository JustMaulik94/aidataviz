# tufte-viz — Edward Tufte data visualization skill

Apply Edward Tufte's data visualization principles to transform a chart description, data, or existing visualization into a cleaner, more analytically effective design.

## Core principles to apply

**1. Maximize data-ink ratio**
Every pixel of ink should carry data. Remove: chartjunk (decorative gradients, drop shadows, rounded rectangles), redundant grid lines, unnecessary borders, background fills that carry no information.

**2. Small multiples over overlapping series**
When comparing N series on a shared axis, separate them into N small panels with a shared scale. The analytical act is comparison — small multiples make it direct. Each panel gets: its own band label (left), a single zero/reference line, and an end-value annotation (right). No legend needed.

**3. Direct labeling — eliminate legends**
Label the data itself. Band or series name on the left; current/final value annotated at the right end of each line. The reader's eye never leaves the data.

**4. Range frame instead of full axis box**
Replace the four-sided chart border with a tick that spans only the actual data range for that panel. This conveys the data extent without the noise of a full axis.

**5. Layering for context**
Add context behind the data, not on top of it. Examples:
- A global/overall average as a light gray line behind each small multiple
- Historical period backgrounds (Medieval Warm Period, Little Ice Age, etc.) as lightly tinted rectangles with italic labels above the plot strip
- A pre-industrial or baseline median as a single horizontal reference line

**6. Dot scatter + running median instead of connect-the-dots**
For noisy time series, plot raw observations as small semi-transparent dots and overlay a 20–30 year running median as a solid line. This separates noise from signal without hiding either.

**7. Invert axes when direction is meaningful**
If "lower = warmer" or "earlier = better", invert the y-axis and state the direction in the axis label (e.g., "Bloom date (earlier ↑)").

**8. Annotate exceptional data points directly**
Circle outliers or record values; attach a short leader line to a label that gives the year and the value. Keep labels in clear space — not overlapping bands, baselines, or other annotations.

**9. Move explanatory prose to captions**
The chart carries only data + landmarks. Interpretation lives in the figure caption below.

## Design vocabulary

| Before | After |
|--------|-------|
| Rainbow N colored lines on shared axes | N small multiples, north→south or logical order, shared y-scale |
| Side legend | Band name at left of panel, value annotated at right end |
| Heavy grid (every 10 units) | Single zero/reference line + range tick at left |
| Colored series lines | Black line for the focal series; gray for context |
| Connected annual line | Semi-transparent dots + 30-yr running median |
| Decorative chart border | None (or hairline only where essential) |
| Chart title inside the frame | Short italic annotation above or below as a caption |

## Output format

When asked to redesign a chart, produce self-contained HTML with an inline SVG. Use:
- `font-family: Georgia, serif` for body text
- `font-family: system-ui, sans-serif` for axis labels and UI text
- Background: `#fdfdfb` (off-white)
- Primary data ink: `#1a202c` (near-black)
- Context/underlay: `#a0aec0` at 60% opacity
- Reference lines: `#cbd5e0` at 50% weight
- Annotations: `#c53030` (red) for current/record values
- Epoch backgrounds: `#fef3c7` (warm), `#dbeafe` (cool), `#fee2e2` (industrial)

Include a "What the skill changed" summary block at the bottom of the page listing each specific design decision made.

## Examples

See `demos/demo__giss-temperature.html` — NASA GISS latitude bands: rainbow lines → small multiples.
See `demos/demo__kyoto-sakura.html` — Kyoto cherry blossom dates: connected line → dot scatter with running median and climate epoch bands.
See `demos/demo__sunspot-butterfly.html` — Sunspot butterfly diagram: SSN line chart → latitude heatmap.
See `demos/demo__sunspot-pretty.html` — Austere vs. beautiful: two valid Tufte aesthetics for the same butterfly data.

## References

See `references/tufte-principles.md` — core principles from *The Visual Display of Quantitative Information*: Lie Factor, data-ink ratio, chartjunk, small multiples, range-frame.
See `references/analytical-design.md` — extensions from *Envisioning Information*, *Visual Explanations*, *Beautiful Evidence*: six analytical design principles, sparklines, layering, micro/macro design.
