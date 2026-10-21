# Calculus B Notes

LaTeX sources for the twelve-chapter Calculus B tutoring notes.

## Contents

- `main.tex`: document entry point.
- `preamble.tex`, `preface.tex`, and `ch1.tex` through `ch12.tex`: shared setup, preface, and chapters.
- Referenced figures, `fig.pptx` (figure source), and `fig9-1.pdf` (vector figure).
- `ch3.5.tex`, `ch4_12.tex`, `ch10_2.tex`, and `preface_w.tex`: supplementary or alternate drafts; not included by `main.tex`.
- `main.pdf`: current compiled handout for reading.

## Build

Use XeLaTeX with a full TeX Live installation (verified with XeLaTeX on TeX Live 2023). The document uses `ctexart`, TikZ, and PGFPlots. The current setup uses Windows CJK fonts; install equivalent fonts or configure the ctex fontset on other systems.

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

Run again if LaTeX requests another pass for references or the table of contents.


## Example format

Examples are numbered automatically as `chapter.sequence`, using the document's section counter. All twelve chapters use the same environments; supplementary drafts use the same definitions but are not included in `main.tex`.

```latex
\begin{example}[2022 B卷]
\label{ex:sample}
Complete problem statement, including all subquestions.
\end{example}

\begin{analysis}
Optional discussion of the approach.
\end{analysis}

\begin{solution}
Complete derivation and conclusion.
\end{solution}
```

- The optional example argument contains the source, such as a year, exam paper, or textbook reference. Omit it when there is no source. Descriptive titles belong in the statement.
- Use `proof` for proof exercises and `solution` for other answers. Both insert their ending square automatically; do not add manual QED symbols.
- For alternative methods, use `\begin{solution}[解法一]`, `\begin{solution}[解法二]`, etc. A method name can follow the heading in Chinese parentheses.
- Put every part of a question inside `example`, and every step and conclusion inside its answer environment. Keep general discussion outside these environments.
- Cite an example as `例\ref{ex:sample}`. Keep labels stable when inserting or moving exercises; never type the displayed number into a reference or figure caption.
- Problem statements use italics (KaiTi for Chinese with the Windows ctex fontset); example headings, source metadata, and analysis/answer text use upright fonts.
- Environment definitions in `preamble.tex` control heading fonts and spacing. Avoid manual vertical padding and forced page breaks around examples.

## Version control

Only lecture sources, selected figure assets, and the current complete PDF are tracked. Auxiliary build files, historical PDF exports, separate exam-solution files, unrelated references, and recovery files stay local. `.gitignore` uses an explicit allowlist; add an exception when adding a new lecture file.

Use brief English commit messages and clear abbreviations, for example:

- `Init notes src & figs`
- `Fix Ch. 7 ex.`
- `Rev. Ch. 10 proofs`
- `Update handout PDF`

Refresh `main.pdf` when publishing changes to the handout.
