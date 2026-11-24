# Demo patch

## Layout

Built by `buildPatch()` (x across, y down):

- (0,0) `clock`: 120 BPM, 4 beats per cycle.
- (1..8,0) `seq`: 8 steps, one cell each.
- Rows y=1..3 are voices `bass`, `mid`, `lead`. Each has 8 `step` cubes at x=1..8, then `phasor` (x=9), `sine` (x=10) and `mix` (x=11).
- (11,4) `out`: -6 dB.
- The mixes chain downward through `S`/`N`, so the voices sum into `out`.

## Content

- Bass starts on a bass clef, the others on treble. All start in C minor; gains are -6, -12 and -16 dB.
- With 4 beats per cycle at 120 BPM, one step lasts 0.25 s.
