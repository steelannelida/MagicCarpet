# MagicCarpet

A web-based constructor kit for musical projects.

## Cube Grid prototype

A web-based environment where a whole track or live setup is built from small square cubes on a 2D grid. Placement is patching: signals flow right and down between neighbouring cubes.

This is a minimal first prototype: a multistep sequencer driving three pure sine voices with gates only (no envelopes).

## Run it

Open `prototype/index.html` in Chrome and press **POWER**. No build step and no server needed.

## What's in the prototype

- **Clock** outputs one ramp for the whole sequence, with BPM and play/stop.
- **Sequencer** turns that ramp into a per-step ramp on each column.
- **Step** cubes show a quarter note on a staff. Drag a note to change its pitch, and the clef switches automatically across the whole C0–C8 range. Click a step to bypass it.
- **Phasor → Sine → Mix** per voice, summed into **Out** (with a soft limiter).

Controls: drag a knob or note, Shift for fine, mouse wheel, double-click a knob to reset.

## Spec

The project is spec-driven: `spec/` describes the current state and is the source of truth. See `spec/README.md`.

## Layout

- `prototype/index.html`: the whole app. Engine (AudioWorklet), patch model and canvas UI are in one file.
- `prototype/test.html`: offline engine test. Run it with
  `chrome --headless --allow-file-access-from-files --virtual-time-budget=60000 --dump-dom prototype/test.html`
  and look for `RESULT: PASS`.

## Known limits

No editing of the grid yet, and there are no envelopes, so steps click at their boundaries. Tested in Chrome only.

## Licence

MIT, see `LICENSE`.
