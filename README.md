# OEFEN Exercise Art

Exercise illustrations used in the [OEFEN](https://oefen.app) fitness app.

## Licence

**Creative Commons Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)**

See [LICENSE](LICENSE) for the full licence text.

## Provenance

The artwork originates as pose drawings from
[Everkinetic](https://github.com/everkinetic/data). Those were redrawn as
three-frame movement illustrations by Bryl Lim for
[Workout Guide](https://github.com/bryllim/workout-guide), and collected into
the form we took them from by
[GymMane](https://github.com/InlitX/GymMane), at commit
`baceaf087cd945ed55b2ab8f1d98fd02e1fb470d`. Each link in that chain licenses
the artwork under CC BY-SA 4.0.

## What OEFEN changed

`scripts/convert_exercise_art.py` (in the OEFEN iOS repository) resolves the
original SVG path `d` strings into absolute cubic Béziers — relative
coordinates made absolute, `H`/`V`/`L` promoted to curves, `S`/`T`
reflections resolved, elliptical arcs converted to Béziers — and writes them
as a compact binary the app decodes without an SVG parser. Coordinates are
rounded to half a unit on the artwork's 512-unit grid.

The drawings themselves are otherwise untouched: no frame was redrawn,
retimed, added, or removed. OEFEN fills them with a theme colour at runtime
rather than shipping a fixed-colour image.

## File format

Each `.bin` file is the compact binary representation of a three-frame
animation. The format is documented in `PhoenixFitness/Design/PFExerciseArtView.swift`
in the OEFEN iOS repository. The Xcode asset catalog structure (`.dataset`
directories with `Contents.json`) is the standard format used by Xcode to
bundle data files into iOS apps.

## Attribution (CC BY-SA 4.0 requirement)

- **Everkinetic** — original pose drawings, CC BY-SA 4.0
  <https://github.com/everkinetic/data>
- **Bryl Lim / Workout Guide** — three-frame animation adaptation, CC BY-SA 4.0
  <https://github.com/bryllim/workout-guide>
- **GymMane / InlitX** — collection into this artwork set, CC BY-SA 4.0
  <https://github.com/InlitX/GymMane>

This repository satisfies CC BY-SA 4.0 § 2(a)(5)(B) for OEFEN's App Store
distribution of these illustrations.
