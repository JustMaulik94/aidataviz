# Tufte Principles — The Visual Display of Quantitative Information

Reference for the `tufte-viz` skill. Drawn from Edward Tufte, *The Visual Display of Quantitative Information* (2nd ed., 2001).

---

## Graphical Excellence

> "Graphical excellence is the well-designed presentation of interesting data — a matter of substance, of statistics, and of design."

Excellence consists of:
- Complex ideas communicated with clarity, precision, and efficiency
- The greatest number of ideas in the shortest time with the least ink in the smallest space
- Multivariate data shown in a way that induces the viewer to think about the substance

The best graphics are those that make the viewer think about the data, not the graphic design.

---

## Graphical Integrity

Graphics can distort the underlying data. Key integrity failures:

### The Lie Factor

```
Lie Factor = (size of effect shown in graphic) / (size of effect in data)
```

A Lie Factor of 1.0 means the graphic is truthful. Values substantially above or below 1.0 indicate distortion.

Common violations:
- Varying icon size in two dimensions when data varies in one
- Changing both height and width of a bar when only one dimension encodes data
- Starting a y-axis at a non-zero value without clearly labeling it
- Using perspective/3-D to inflate visual effect

### Six Principles of Graphical Integrity

1. Representation of numbers should be directly proportional to the numerical quantities represented
2. Clear, detailed, and thorough labeling should be used to defeat graphical distortion and ambiguity
3. Show data variation, not design variation
4. In time-series displays of money, standardize units (constant dollars)
5. The number of information-carrying dimensions depicted should not exceed the number of dimensions in the data
6. Graphics must not quote data out of context

---

## Data-Ink Ratio

> "Data-ink is the non-erasable core of a graphic, the non-redundant ink arranged in response to variation in the numbers."

```
Data-ink ratio = Data-ink / Total ink used to print the graphic
```

**Maximize the data-ink ratio**, within reason.

Two erasure principles:
1. Erase non-data-ink, within reason
2. Erase redundant data-ink, within reason

This leads to redesigns that remove:
- Background grid lines (especially heavy ones)
- Box borders around the entire chart frame
- Tick marks that repeat axis values already labeled
- Duplicate y-axis on the right side
- Unnecessary legends (replace with direct labels)
- Axis labels that repeat units already in the title

---

## Chartjunk

Three categories of non-data ink that obscure rather than reveal:

### 1. The Vibration Effect
Unintentional optical art — busy patterns that create visual vibration. Heavy crosshatching, dense moiré patterns, alternating stripes.

### 2. The Grid
Heavy grids compete with the data. Guidelines: use very light grids only when needed for reading values at a distance. Prefer no grid to a grid.

> "The grid should be thought of as a zero-data element — ink that takes up space but adds no data."

### 3. The Duck
When a graphic is decorated in a way that the design structure itself carries no information — when the structure is a duck. Named after a duck-shaped building on Long Island.

Avoid: drop shadows, 3-D effects, decorative borders, gradient fills, superfluous icons.

---

## Small Multiples

> "Small multiples are economical: for a fixed amount of space, a large number of multiples can be arrayed at high data density."

Small multiples:
- Show the same graphic design repeated across different conditions or subgroups
- Share the same scale for direct visual comparison
- Allow detection of pattern, exception, and variation across the multiples
- Eliminate the need for complex legends

Design rules:
- Panels should be small enough that the eye can compare them directly
- Use a shared y-axis scale unless the variation within each panel is the point
- Order panels meaningfully (geographic, magnitude, chronological)
- Label each panel directly — no index, no legend

The number of multiples is limited by the printing area and the minimum legible size. Tufte has shown multiples as small as postage stamps.

---

## Data Density

**Data density** = number of entries in the data matrix / area of the data graphic

High data density is generally desirable. The eye and mind can process very dense information if it is well organized.

Reference: the newspaper weather map achieves very high data density (temperature, pressure, fronts, precipitation, wind) in a small space using layered, integrated graphics.

The **shrink principle**: a good graphic remains legible when reduced to a thumbnail. If it falls apart when shrunk, it contains too little data relative to its decorative elements.

---

## Multifunctioning Graphical Elements

> "Mobilize every graphical element, including the grid, to show the data."

Graphical elements should serve multiple roles:

- **The range-frame**: axis lines that span only the observed data range, not from 0 to maximum. The tick marks themselves become a one-dimensional scatter plot.
- **The dot-dash plot**: a scatter plot with marginal tick marks (one per observation) along each axis, giving a built-in rug plot
- **The data rectangle**: size of the plotting area encodes the range of the data, not an arbitrary box

The goal is to eliminate elements that carry zero information while giving all retained elements maximum information load.
