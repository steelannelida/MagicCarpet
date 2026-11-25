# Unsorted ideas/future features

## Model

* Cube on/bypass can have different meaning depending on cube
* Multiple planes, talking through portals
  * Short-circuit portals (single-sample delays) allowed only within 1 plane
  * Planes can run on different CPU cores
* Frozen regions (rect or unspecified)
* Phantoms
* Polyphonic regions
* Action history
* Cubes can swap inputs, outputs or both - at least for 1x1
* Dashboards
* Presets for subregions or planes
  * Application after layout/routing changes?
  * Or the cubes/routing within the region is also remembered
  * Preset manager is another cube. Its state is the current preset number

### Where do the projects live

* Local storage
* Save/load local files
* JSON internal format
* Eventually server-side: private or public,

### Samples and other resources

* Upload (verify CC license, or maybe a partner website?)
* Adding by link to the library

### Cube spec:

* Codename, display name, symbol, help description
* Shape & size (including variable dims)
* Signal interpretation for each I and O
* Knob or UI spec: range, interpretation, UI presentation
    * Input attenuation or disabling
* Graphics as inlined SVG
* Properties & settings accessible via inspector
* Actions on user interation (knobs behave standardly)
* Operation: what each output is equal to when on and when off
  * Default: passing unattenuated N to S in both modes, passing W to E when off


### Signals

* Ramp
* Real-time
* Note: off = 0, on = unwrapped phase, starting above 1
* Gate + velocity: 0 = off, `(0:1]` - on with velocity
* Audio
* Chord/: bitmap of on notes
* Midi: 2 or 3 minor bytes in the 32; message is transmitted once, 0 is silence.
* Generic control (modulation): mostly -1..1, but can take arbitrary
* Integer: for routing, preset selection etc.

## Engine



## UI

### Layout

### Look

We need to specify how to display differences in the following categories. It is necessary that those are seen at different zooms

Cubes:
* Type: cube color matches category, display symbol if there's space. Full type name isn't visible when zoomed out
* On/off: cube's brightness



Edges:
* Color at the edge indicates signal type
* Color of the triangle indicates signal level stats
* Muted or attentuation: ?

### Navigation

### Tools/Operations


## Cubes

### Math

Cubes that take arbitrary signal types.

Visual: If there's 1 input or input matches, output is colored the same as input.

### Local routing & Mixing

### Synth voice blocks

### Sampling

### Audio processing

### Sequencing, time manipulation

### Communication/Portals

### IO

### Interface/visualisation

### MIDI

### Note operations

### Conversion

## Library



## How do we implement?


