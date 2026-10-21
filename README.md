# Calculus B Notes

LaTeX sources for the twelve-chapter Calculus B tutoring notes.

## Contents

- `main.tex`: document entry point.
- `preamble.tex`, `preface.tex`, and `ch1.tex` through `ch12.tex`: shared setup, preface, and chapters.
- Referenced figures, `fig.pptx` (figure source), and `fig9-1.pdf` (vector figure).
- `ch3.5.tex`, `ch4_12.tex`, `ch10_2.tex`, and `preface_w.tex`: supplementary or alternate drafts; not included by `main.tex`.
- `main.pdf`: current compiled handout for reading.

## Build

Use XeLaTeX with a full TeX Live installation (verified with two XeLaTeX passes on TeX Live 2023; 306 pages). The document uses `ctexart`, TikZ, and PGFPlots. The current setup uses Windows CJK fonts; install equivalent fonts or configure the ctex fontset on other systems.

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

Run again if LaTeX requests another pass for references or the table of contents.

## Version control

Only lecture sources, selected figure assets, and the current complete PDF are tracked. Auxiliary build files, historical PDF exports, separate exam-solution files, unrelated references, and recovery files stay local. `.gitignore` uses an explicit allowlist; add an exception when adding a new lecture file.

Use brief English commit messages and clear abbreviations, for example:

- `Init notes src & figs`
- `Fix Ch. 7 ex.`
- `Rev. Ch. 10 proofs`
- `Update handout PDF`

Refresh `main.pdf` when publishing changes to the handout.
