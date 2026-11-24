# Spec

The spec describes the project as it is now. It is the source of truth: a change to the spec is a task, and the commit that implements it contains the spec diff, the code and the tests.

## Rules

- One concern per file, short normative bullets, no history (git has that).
- Known gaps and undecided points go under an `Open` heading in the file they belong to. Status is not tagged; it is implied by the text.
- If code and spec disagree, fix the code, unless the commit changes both on purpose.
- Commit messages name the spec files touched.
- Cube categories are not fixed. Move cubes between category files freely.

## Index

| File | Content |
| --- | --- |
| [grid.md](grid.md) | cells, ports, edges |
| [signals.md](signals.md) | signal scales |
| [engine.md](engine.md) | audio processing |
| [protocol.md](protocol.md) | messages between UI and engine |
| [ui.md](ui.md) | rendering, notation, interaction |
| [platform.md](platform.md) | browser, packaging, power |
| [demo-patch.md](demo-patch.md) | the built-in patch |
| [testing.md](testing.md) | what is verified and how |
| [cubes/](cubes/README.md) | one file per cube category |
