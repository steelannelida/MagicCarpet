# UI

## Grid and layout

- Canvas 2D, fitted to the window and centred (no pan or zoom yet). Cells are flush squares.
- Light-gray grid lines run across the whole canvas, aligned with the cells.
- Text stickers can label cells (demo patch only).

## Colour

Hue shows the expected scale: ramp cyan, phase amber, audio magenta, master green. The grid is drawn dimmed while the engine is off.

## Connections

- A connected input is shown by a blunt-nosed triangle inside the receiving cube, on its `W` edge pointing east or on its `N` edge pointing south. There are no connector lines.
- The triangle takes the hue of the producing port. It is dim at rest and brightens with the edge's peak level.

## Interaction

- Knob: drag vertically (full range in 200 px), Shift = one tenth, wheel = one step, double-click = back to the initial value.
- Step: drag anywhere on the cube to change pitch (6 px per semitone); a click under 3 px toggles bypass.
- Clock: click the cube to play or stop; drag the knob for tempo.
- Edits never reset phase or restart sound.

## Notation

- A step shows its note as a quarter note on a five-line staff that runs edge to edge. Every step draws its own clef.
- Pitch is rounded to the nearest semitone for drawing and spelled with flats. A fractional pitch adds cents to the readout under the staff.
- Bypassed steps draw a hollow, dim note. The playing step is lit and shows a playhead line.
- Clefs: bass 15mb, bass 8vb, bass, treble, treble 8va, treble 15ma, each with its bottom line pitch. A step keeps its clef while the note lies within five staff positions below to thirteen above its bottom line. Outside that, it takes the clef whose staff centre is nearest. Octave clefs print an "8" or "15".
- Clef glyphs use the system's musical symbol font.

## Open

- Quarter note length is only illustration: steps have no duration.
