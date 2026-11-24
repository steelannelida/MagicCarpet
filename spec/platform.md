# Platform

## Packaging

- The app is one file, `prototype/index.html`, with no build step. Scripts are separate blocks: the engine, the patch model and the UI.
- The engine block is plain text; it is loaded into an AudioWorklet from a Blob URL.

## Power

- The audio engine is off until the user presses POWER. The first press creates the AudioContext and the worklet; later presses suspend and resume it, keeping all state.
- There is no transport; play and stop belong to the clock cube.

## Browsers

- Developed and tested in Chrome on macOS. Other browsers are untested.
