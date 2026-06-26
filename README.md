# Lacamas Watershed Council — LaTeX Document Template

A LaTeX template for LWC reports, program documents, and papers.

## Directory structure

```
latex-paper-template/
├── paper.tex         # Main document — edit this
├── appendix.tex      # Optional standalone appendix
├── figures/          # Place image files here
├── style/
│   ├── paper.sty     # Main LaTeX style (do not edit)
│   ├── paper.bst     # BibTeX bibliography style (do not edit)
│   └── appendix.sty  # Appendix style (do not edit)
└── refs/
    └── paper.bib     # Bibliography entries — add references here
```

## Usage

1. Edit `paper.tex` — replace title, author, date, and body text.
2. Add image files to `figures/` and reference them with `\includegraphics{figures/filename}`.
3. Add bibliography entries to `refs/paper.bib`.
4. Compile:

```bash
pdflatex paper.tex
BSTINPUTS=style: bibtex paper
pdflatex paper.tex
pdflatex paper.tex
```

If the document has no bibliography, a single `pdflatex paper.tex` is sufficient.

## Online appendix

To compile the standalone appendix:

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
