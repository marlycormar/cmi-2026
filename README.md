![Lean](https://img.shields.io/badge/Lean-v4.29.0--rc2-blue)
![mathlib](https://img.shields.io/badge/mathlib-v4.29.0--rc2-blue)

# CMI 2026

This repo contains the [CMI 2026](https://sites.mit.edu/cmi2026/) lecture-note [blueprint](https://github.com/PatrickMassot/leanblueprint) site. These notes are constantly being updated, so use them at your own risk. Feel free to report any issues/errors by creating an issue.

The blueprint sources live under [blueprint/src](./blueprint/src). The content file there imports `main.tex`, so the notes can still be edited in one place.

Typical local commands:

```sh
./.venv/bin/leanblueprint pdf
./.venv/bin/leanblueprint web
./.venv/bin/leanblueprint all
lake update checkdecls
lake -R -Kenv=dev update doc-gen4
lake build
lake exe checkdecls blueprint/lean_decls
```
