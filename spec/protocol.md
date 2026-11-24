# Protocol

UI and engine talk only through these messages, so the engine can live anywhere.

## Port names

`E`, `W`, `S<j>`, `N<j>` where `j` is the cell index inside the cube.

## UI to engine

- `{t:'topo', topo}` where `topo = {cubes:[{id,type,w,knob,on,params}], edges:[{from,out,to,inp}]}`. Sent once when the engine starts.
- `{t:'cmd', cmd}` where `cmd = {op:'setKnob', id, value}` or `{op:'setOn', id, value}`.
- Every edit goes through one `dispatch(cmd)`: it is appended to a command log, applied to the UI model and sent to the engine.

## Engine to UI

- `{t:'stats', pk[], last[]}`, indexed like `topo.edges`.

## Open

- Topology changes after start are supported by the engine but nothing sends them yet.
