![Lean](https://img.shields.io/badge/Lean-v4.29.0--rc2-blue)
![mathlib](https://img.shields.io/badge/mathlib-v4.29.0--rc2-blue)

# CMI 2026

This repo contains the [CMI 2026](https://sites.mit.edu/cmi2026/) lecture-note blueprint site. These notes are constantly being updated, so use them at your own risk. Feel free to report any issues/errors by creating an issue.

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

## Updating The Dependency Graph

The dependency graph is generated from annotations in [main.tex](./main.tex).
For each important theorem-like item, add a stable label and, when appropriate,
its dependencies:

```tex
\begin{definition}\label{def:submonoid}
  ...
\end{definition}

\begin{proposition}\label{prop:image-submonoid}
\uses{def:monoid-homomorphism,def:submonoid}
  ...
\end{proposition}
```

Useful commands:

- `\label{...}` gives the node a stable name.
- `\uses{...}` adds edges from prerequisite results to the current result.
- `\proves{...}` optionally records forward targets.
- `\lean{...}` optionally links the statement to a Lean declaration.

Use labels such as `def:...`, `prop:...`, `lem:...`, and `thm:...`, and prefer
lowercase hyphenated names without spaces.

After editing `main.tex`, regenerate the HTML blueprint and dependency graph:

```sh
./.venv/bin/leanblueprint web
```

If you also want the PDF rebuilt:

```sh
./.venv/bin/leanblueprint all
```

## Acknowledgments

We express our sincere gratitude to [Dr. Felix Gotti](https://math.mit.edu/~fgotti/) for his dedication in authoring the CMI 2026 notes in LaTeX. His careful exposition and sustained effort form the core material on which this blueprint site is built.

We also gratefully acknowledge the developers and maintainers of [Lean](https://github.com/leanprover/lean4) and [Blueprint](https://github.com/PatrickMassot/leanblueprint), whose tools make this project possible.
