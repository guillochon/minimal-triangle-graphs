# Minimal Triangle Graphs — OEIS A000080

**https://guillochon.github.io/minimal-triangle-graphs/**

[A000080](https://oeis.org/A000080) counts minimal triangle graphs: sets of triangles on n points that join
everything up, with no triangle to spare (removing any one disconnects something), up to relabelling the points.
1, 1, 2, 4, 9, 19, 48, 117, 307, … for n = 3, 4, 5, … [A048781](https://oeis.org/A048781) adds up their
triangles. The OEIS lists both up to n = 25 (Martin Fuller, 2015, about a day of isomorph-free search). The counts
from n = 26 on are new, computed by an exact formula in
[oeis-results/A000080](https://github.com/guillochon/oeis-results/tree/main/A000080).

The page shows every minimal triangle graph up to n = 9, random examples for n = 10 to 40, and the counts table.

- **Colours.** Grey triangles are *lone* triangles. Each coloured group is a *block*: points joined in a
  multigraph with no cut point (several triangles may run along one pair of points), where every triangle
  sticks out one private corner. The structure theorem says every minimal triangle graph is a tree of lone
  triangles and blocks glued at points, and that is what makes the counting formula possible.
- **New examples** draws a fresh set; the switch turns block colouring off.

## How it works

Everything runs in the browser, in one file (`index.html`).

- **Small n.** The full lists for n ≤ 9 come from Martin Fuller's program on the OEIS entry, with blocks
  labelled from the incidence graph.
- **Sampling.** A random tree of units: lone triangles, and blocks built as a random open ear decomposition of a
  2-connected loop-free multigraph (every block has one), each edge given its own corner point. Units are glued
  at random existing points until there are exactly n. Every minimal triangle graph can arise, but not with equal
  probability.
- **Layout.** A spring layout of the point–triangle incidence graph, drawn as translucent triangles.

Made by James Guillochon with Claude. The source lives in the oeis-sniper project (`viz/A000080/`); this repo holds
the published copy.
