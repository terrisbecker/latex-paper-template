# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A LaTeX document template for the Lacamas Watershed Council (LWC). `paper.tex` and `appendix.tex` at the root are the canonical templates. Real documents live under `docs/<folder-name>/` and inherit shared style files from `style/`.

## Compiling documents

**A document under `docs/<folder-name>/`:**
```bash
cd docs/<folder-name>
pdflatex paper.tex
bibtex paper          # only if the document has a bibliography
pdflatex paper.tex
pdflatex paper.tex
```

**The root template (from repo root):**
```bash
pdflatex paper.tex
BSTINPUTS=style: bibtex paper
pdflatex paper.tex
pdflatex paper.tex
```

**The standalone appendix (from repo root, after compiling `paper.tex`):**
```bash
pdflatex appendix.tex
BSTINPUTS=style: bibtex appendix
pdflatex appendix.tex
pdflatex appendix.tex
```

The appendix uses `\externaldocument{paper}` to cross-reference labels from `paper.tex`, so `paper.aux` must exist in the same directory first.

## Style files

`style/paper.sty`, `style/paper.bst`, and `style/appendix.sty` are shared across all documents. Do not edit them unless changing the global style for all documents.

- Root template references them as `style/paper` (relative to root).
- Documents under `docs/<folder-name>/` reference them as `../../style/paper`.

## Starting a new document

Use the `/new-doc` skill: it creates `docs/<folder-name>/`, copies `paper.tex`, fixes style paths, and adds `figures/.gitkeep`.

## Reviewing documents

Use the `/doc-review` skill. It checks grammar, clarity, consistency, loopholes, and alignment with LWC bylaws and charter (references in `.claude/skills/doc-review/references/`). It commits each category of fix separately and opens a pull request when done.

## Citation style

Citations use `natbib` with author-year style (no separator). Use `\citep{authorYY}` for parenthetical and `\citet{authorYY}` for inline. Bibliography entries go in a `paper.bib` file in the document folder (or `refs/paper.bib` for the root template).
