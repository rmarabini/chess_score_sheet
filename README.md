# Chess Score Sheet (LaTeX)

A printable chess score sheet built in LaTeX.
It includes header fields (Event/Round, Date/Board, White/Black), a moves grid with two
columns per move (White & Black), a result row with checkboxes, and signature blocks.

---

## Features

---

## Requirements

- A LaTeX distribution (**TeX Live** / **MiKTeX**).
- Packages:
  - `tabularx`, `array` (table/columns)
  - `tikz` (for `\foreach` loops)
  - `amssymb` (checkbox `\square`)
  - `arydshln` (dashed lines)
  - `collcell` (baseline adjustments)
  - `geometry` (fix margins)

Install via your distribution’s package manager if missing.

---

## Quick Start

   Either use the precompiled pdf files  or execute

```bash
pdflatex your_scoresheet.tex
```


## Customization

**change paper size from a4 to letter**

`\documentclass[15pt,letterpaper]{article}` 

**Number of move rows**
- Change `\newcommand{\nRows}{60}` to your desired count.

**Column alignment**
- Center numeric columns (first & fourth) using `>{\centering\arraybackslash}p{2em}`.
- Center headers with `\multicolumn{1}{c|}{...}`.

**Proportional header widths**
- Adjust `Y{fraction}` values: `Y{0.75}|Y{0.25}`, `Y{0.5}|Y{0.5}`, etc.

**Result checkboxes**
- Provided by `amssymb` as `\(\square\)`. Make larger: `\Large`.

**Signature cell height**
- Control with `\rule{0pt}{2.5em}`; for top alignment: `\parbox[t]{\linewidth}{...}`.

**Thicker borders**
- Use `!{\vrule width <length>}` in the table spec.

**Dashed rules (optional)**
- With `arydshln`, use `:` for dashed verticals and `\hdashline` for dashed horizontals.

---

## Troubleshooting

**Undefined control sequence `\square`**
- Load `amssymb` and use math mode: `\(\square\)`.



## Variants & Next Steps

- **Spanish labels** (Evento, Ronda, Fecha, Mesa, Blancas, Negras):

## Produce two copies in a single page (in linux systems)

`pdfjam --nup 2x1 --landscape kk.pdf 1,1,1,1 --a4paper -o duplicated_page.pdf`
`pdfjam --nup 2x1 --landscape kk.pdf 1,1 --a4paper -o duplicated_page_duplex.pdf`



