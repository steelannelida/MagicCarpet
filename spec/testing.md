# Testing

## Offline engine test

`prototype/test.html` loads the engine and patch model from `index.html` and renders 4 s at 48 kHz without an audio device. It checks:

- all cubes are scheduled and the output has no NaN;
- in every step, each voice has the expected amplitude at its note (within 25 %) when its step is on and under 0.02 when it is off;
- after the clock stops, the output is silent.

Run: `chrome --headless --allow-file-access-from-files --virtual-time-budget=60000 --dump-dom prototype/test.html` and look for `RESULT: PASS`.

## Gaps

No tests for the UI, interaction, notation or real audio output. Those are checked by hand.
