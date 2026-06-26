---
name: new-doc
description: Initialize a new document folder under docs/ from the root template.
---

i. Preamble. This skill creates a new document folder under `docs/` and copies the root template into it, ready to compile. It does not open or edit the document — it only sets up the folder structure.

ii. Arguments. The user provides a single folder name (e.g. `board-meeting-2026`). If no argument is given, ask the user to provide one. If the folder `docs/<folder-name>` already exists, stop and tell the user — do not overwrite it.

** Begin initialization **

1. Validate. Confirm that `docs/<folder-name>` does not already exist. If it does, report this to the user and stop.

2. Create folder tree. Create the following directories:
   - `docs/<folder-name>/`
   - `docs/<folder-name>/figures/`

3. Copy template. Copy the root `paper.tex` into `docs/<folder-name>/paper.tex`.

4. Fix style paths. In the copied `docs/<folder-name>/paper.tex`, make the following two replacements so pdflatex can find the shared style files:
   - `\usepackage{style/paper}` → `\usepackage{../../style/paper}`
   - `\bibliographystyle{style/paper}` → `\bibliographystyle{../../style/paper}`

5. Add figures placeholder. Create an empty file `docs/<folder-name>/figures/.gitkeep` so the figures directory is tracked by git.

6. Confirm. Report the folder tree that was created and remind the user to:
   - Edit `docs/<folder-name>/paper.tex` to fill in title, author, date, and body text.
   - Add a `paper.bib` file to the folder if bibliography entries are needed.
   - Compile from the document folder with `pdflatex paper.tex`.
