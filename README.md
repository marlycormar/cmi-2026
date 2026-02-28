# CMI 2026

This repo contains the CMI 2026 lecture-note blueprint site.

It is for deploying the `leanblueprint` version of [main.tex](./blueprint-cmi/main.tex).

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
