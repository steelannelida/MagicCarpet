# Grid

## Cells and cubes

- The grid is a sparse lattice of square cells at integer (x, y); x grows right, y grows down.
- A cube has a stable string `id`, a `type`, a position, a width `w` in cells (height is always 1), a `knob` value in its own units, an `on` flag and optional `params`.
- Cube state belongs to the `id`, never to the position.

## Ports

- Inputs: `W` (left) and `N` (top). Outputs: `E` (right) and `S` (bottom).
- A multi-cell cube has `W` on its leftmost cell and `E` on its rightmost. Every cell has its own `N` and `S` (`N0..`, `S0..`).
- A cube that does not define `S` passes `N` to `S` unchanged.

## Edges

- Edges come only from adjacency: `E` of a cube's rightmost cell feeds the `W` of the cube in the next cell to the right; `S` of a cell feeds the `N` of the cell below.
- An empty cell passes nothing; an unconnected input reads 0.
- Edges have no delay, no gain and cannot be muted. The graph is a DAG by construction.
- The rule is the pure function `computeEdges(cubes)`.

## Open

- Cubes taller than one cell.
