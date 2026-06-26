# Lacamas Watershed Council — LaTeX Document Template

A LaTeX template for LWC reports, program documents, and papers.

## Directory structure

```
latex-paper-template/
├── paper.tex              # Template — copy into docs/<folder>/ to start a new document
├── appendix.tex           # Optional standalone appendix template
├── figures/               # Template placeholder for figures
├── style/
│   ├── paper.sty          # Main LaTeX style (do not edit)
│   ├── paper.bst          # BibTeX bibliography style (do not edit)
│   └── appendix.sty       # Appendix style (do not edit)
├── refs/
│   └── paper.bib          # Template bibliography entries
└── docs/
    └── upper-watershed-committee/
        ├── paper.tex      # Upper Watershed Committee document
        └── figures/       # Figures for this document
```

## Starting a new document

1. Create a folder under `docs/`: `docs/<folder-name>/`
2. Copy `paper.tex` into the new folder.
3. In the copied `paper.tex`, update the style paths:

```latex
\usepackage{../../style/paper}
\bibliographystyle{../../style/paper}
```

4. Edit the title, author, date, and body text.
5. Add a `paper.bib` file in the same folder for bibliography entries (if needed).
6. Place figure files in a `figures/` subfolder (if needed).

## Compiling a document

From the document's folder:

```bash
cd docs/<folder-name>
pdflatex paper.tex
bibtex paper               # only if the document has a bibliography
pdflatex paper.tex
pdflatex paper.tex
```

If the document has no bibliography, a single `pdflatex paper.tex` is sufficient.

## Compiling the template

From the repo root:

```bash
pdflatex paper.tex
BSTINPUTS=style: bibtex paper
pdflatex paper.tex
pdflatex paper.tex
```

## Online appendix

To compile the standalone appendix template (from the repo root):

```bash
# Compile the main document first to generate paper.aux
pdflatex paper.tex
BSTINPUTS=style: bibtex paper
pdflatex paper.tex

# Then compile the appendix
pdflatex appendix.tex
BSTINPUTS=style: bibtex appendix
pdflatex appendix.tex
pdflatex appendix.tex
```

The appendix can cross-reference labels from `paper.tex` as long as `paper.aux` is present in the same directory.

## License

This template is based on [latex-paper](https://github.com/pmichaillat/latex-paper) by Pascal Michaillat, licensed under the MIT License.
