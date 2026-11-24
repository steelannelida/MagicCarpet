# Mixing

## Mix

- Type `mix`. Knob: gain in dB, -60..6, step 0.5; at -60 the gain is 0.
- `E` = `W`. `S` = `N + W * gain`.

## Out

- Type `out`. Knob: master gain in dB, -60..0, step 0.5.
- `E` = `tanh(gain * (W + N))`, the soft limiter. `E` is what the engine plays. `S` = 0.
