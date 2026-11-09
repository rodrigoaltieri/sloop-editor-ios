# Sloop editor — iOS Web MIDI fix

Copy of the offline editor from [isod89/sloop-fm1](https://github.com/isod89/sloop-fm1) (commit `bac9c05`), GPL-3.0.

Only change: the MIDI port lists (`access.inputs` / `access.outputs`) are read with a `midiList()` helper instead of `[...map.values()]`.
The iOS Web MIDI shim used by apps like Web MIDI Browser returns port maps that have `forEach`/`values()` but no
`Symbol.iterator`, so the original code threw and the editor stayed on "connecting".

Open `https://rodrigoaltieri.github.io/sloop-editor-ios/` in the MIDI browser app.
