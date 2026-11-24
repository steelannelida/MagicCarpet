# Sequencing

## Clock

- Type `clock`. Knob: tempo in BPM, 20..300, step 1. Param `beats`: beats per cycle. `on` = playing.
- `E`: a ramp over the whole cycle, period `beats * 60 / BPM` seconds. While stopped it is 0 and the position resets, so playing starts from the beginning. Tempo changes are smooth.
- `S` = `N`.

## Sequencer

- Type `seq`, width = number of steps, no knob.
- `W`: the cycle ramp, 0 = idle.
- `S_j`: while the ramp is inside the j-th of N equal parts, the position within that part as a ramp; otherwise 0. The index is `ceil(W * N) - 1`.
- `E` = `W`.

## Step

- Type `step`. Knob: pitch in semitones, 0 = C0, 0..96, step 1. `on` = active, otherwise bypass.
- `S` = `N` always.
- While `N > 0` an internal phase accumulates at `16.3516 * 2^(pitch/12)` Hz and runs on; while `N = 0` it is 0.
- `E` = the accumulator when `on` and `N > 0`, otherwise `W`. In a row only one column plays, so the last step's `E` is the active step's unwrapped phase, or 0 when the playing step is bypassed.
- Display and interaction: see [ui.md](../ui.md).
- Missing: no envelope, so steps click at their boundaries; no step length.
