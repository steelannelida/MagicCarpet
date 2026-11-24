# Engine

## Interface

- A single class (`Engine`) with no UI or platform dependency. It takes a topology (see [protocol.md](protocol.md)) and commands, and renders mono blocks.
- Output = the sum of the `E` buffers of all `out` cubes, copied to both channels.

## Scheduling

- Blocks of 128 samples. Cubes run once per block in topological order (Kahn). Each cube processes the whole block.
- Every connected input points at the producer's buffer; unconnected inputs point at a zero buffer.

## Patch swap

- A new topology is applied between blocks. Cubes with the same `id` and `type` keep their state; new cubes start at zero.

## Knob smoothing

- Each block the smoothed knob value moves toward the target by a one-pole filter (about 5 ms). Inside the block, cubes interpolate linearly from the old to the new value.
- Unit conversion (dB to gain, semitones to Hz) happens inside the cube.

## Statistics

- For every edge the engine records the peak |value| and the last value of each block. The worklet posts them about every 2048 samples; peaks restart after posting.

## Open

- Determinism: cubes use `Math.sin`, `Math.pow` and `Math.tanh`, which are not bit-identical across platforms.
