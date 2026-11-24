# Signals

## Format

- Every port carries one float per sample. Buffers are 128 samples, Float64 (so unwrapped phase keeps precision).
- No clamping between cubes; only `out` limits.

## Scales in use

| Signal | Meaning |
| --- | --- |
| Ramp | `(0,1]` while something is playing, `0` when idle. The first sample of a ramp is a small positive number. |
| Phase | unwrapped, in cycles, starts above 0 |
| Wrapped phase | `[0,1)` |
| Pitch (knob only) | semitones, 0 = C0 (48 = C4) |
| Audio | nominally -1..1 |

## Open

- Gain as a signal; Float32 vs Float64 for the C++ engine.
