# blueprint-cmi

This repo is for deploying the `leanblueprint` version of [main.tex](/Users/marlygotti/Dropbox/Academics/MIT/CMI/2026-Spring/meetings/blueprint-cmi/main.tex).

The blueprint sources live under [blueprint/src](/Users/marlygotti/Dropbox/Academics/MIT/CMI/2026-Spring/meetings/blueprint-cmi/blueprint/src). The content file there imports `main.tex`, so the notes can still be edited in one place.

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

To publish the blueprint on GitHub Pages, make sure the repository settings use GitHub Actions as the Pages source.
