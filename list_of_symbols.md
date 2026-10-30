# Build a list of symbols for the thesis front matter

Instructions for the agent doing this work. Read the whole file before starting.

## Why this is needed

The thesis gathers five independent papers. A symbol rename has just been
applied across all of them, and `symbol_replacements.md` records every choice.
The notation is now deliberate, but some letters still carry different meanings
in different chapters, because the quantities really are different. `Q` against
`\mathcal{W}` for the Okubo-Weiss parameter, `D` against `\epsilon` for
dissipation, bold upright against bold italic `u` in the thermalisation chapter.

A reader meeting `A` in one chapter and `A` in another has no way to tell they
are different objects. The list of symbols fixes that.

## What to build

Build **three** files.

**1. `symbols_full.tex`** — every symbol a reader could need, roughly 330 rows.

**2. `symbols_short.tex`** — the principal symbols only, roughly 130 rows.

Keep these as two separate files. Do not build one file with a switch inside
it. The two are meant to be compared and one of them chosen later, so each has
to stand on its own.

**3. The edit to `main.tex`** that imports one of them on the fly. Insert these
lines between `\listoftables` on line 31 and `\mainmatter` on line 33, matching
the pattern the two existing lists already use:

```latex
\cleardoublepage
\phantomsection
\addcontentsline{toc}{chapter}{List of Symbols}
\input{symbols_full.tex}
%\input{symbols_short.tex}   % swap the comment to use the short list
```

Switching list is then one comment character, with no other edit anywhere, and
no extra compilation pass.

Also add `\usepackage{longtable}` to `preamble.tex`. The list runs over several
pages and an ordinary `tabular` cannot break across a page. `booktabs` is
already loaded at line 26 and supplies the rules. Do not load `nomencl` or
`glossaries`; both need a separate `makeindex` run, which this build does not
have.

**Because there are two files, a correction made in one has to be made in the
other.** Say so in a comment at the top of each file.

## Build the inventory yourself

Read these, and work out the current notation from the sources rather than from
memory:

| Read | For |
|---|---|
| `chapters/internal_tide_eddy.tex` and `chapters/appendix.tex` lines 10-295 | Tides |
| `chapters/thermalization.tex` | Thermalisation (no appendix) |
| `chapters/inertial_caustics.tex` and `chapters/appendix.tex` lines 297-316 | Inertial |
| `chapters/active_caustics.tex` and `chapters/appendix.tex` lines 318-477 | Active |
| `chapters/polydisperse_lucky_drops.tex` and `chapters/appendix.tex` lines 479-693 | Droplets |
| `chapters/macros_internal_tide_eddy.tex` | the Tides chapter's own macros |
| `preamble.tex` | the shared macros |
| `symbol_replacements.md` | the agreed meaning of every renamed symbol |

Report each symbol **in the form the reader sees, not the form the source
writes**. `\mb` is `\mathbb`, `\mc` is `\mathcal`, `\ms` is `\mathscr`, and both
`\vec` and `\vect` are `\boldsymbol`. In the Tides chapter `\bs` is bold, `\hat`
is `\widehat`, `\bar` is `\overline` and `\t` is `\widetilde`.

Where an inventory and `symbol_replacements.md` disagree, the markdown wins.

## Traps that are easy to get wrong

- In Thermalisation, `\vec{u}` bold italic is the untruncated Euler velocity and
  `\mathbf{u}` bold upright is the Galerkin-truncated one. Two different fields,
  parted only by slant. Both need a row, and the conventions block must say what
  the slant means.
- In Inertial, `\mathbb{A}` is the fluid gradient tensor while the plain letter
  A names avoider particles, in the same chapter.
- In Droplets, `\lambda` carries three meanings: `\lambda_s` the depletion rate
  of the small droplets, `\lambda(m,m',t)` the Smoluchowski collision kernel,
  and `\bar\lambda` a Poisson mean in the appendix. All three need rows.
- In Active, `\nu` is the kinematic viscosity and nothing else. Line 174 once
  used it for a caustics scaling exponent and now writes that number out, as
  `R = t^{2/3}`, so no exponent row is needed.
- In the Inertial appendix, `\chi` is an auxiliary root of a quartic, not a
  vorticity. The vorticity is `\zeta`.
- In Droplets, italic `m` is the droplet mass and upright `\mathrm{m}` is a
  simulation-unit parameter setting the Kolmogorov length.
- In Active, `\beta` is the swimming rate, so `1/\beta` is the time a swimmer
  takes to cover its own length. `\mu` is the Stokesian mobility and `\mu_E` the
  Ekman friction.

## Order and layout, the same in both files

One alphabetical sequence, in three blocks.

1. **Latin letters**, upper and lower case interleaved alphabetically, so `A`,
   `a`, `B`, `b` and so on. A reader hunting a letter does not care about case.
2. **Greek letters**, in Greek alphabetical order.
3. **Accents, subscripts and conventions**, the things that are not letters. The
   hat for a Fourier amplitude, the overbar for a time average in one chapter
   against angle brackets elsewhere, bold italic against bold upright,
   blackboard bold for a tensor.

Three columns: the symbol, its meaning, the chapter. Where a letter carries more
than one meaning, give each meaning its own row, adjacent, with different
chapters named. So `A` appears twice.

**Use chapter tags, not numbers.** The column holds a short word: Tides,
Thermalisation, Inertial, Active, Droplets, and `all` for anything shared.
Numbers would be wrong the moment a `\subfile` line moves. `\ref` would be
cleaner still but `thermalization.tex` carries no chapter label, and adding one
would mean editing a chapter.

Keep each meaning under about twelve words, so a row does not wrap.

## What the short list drops

Everything used once, every dummy index, and every coefficient that lives only
inside one derivation, for example `a_0, a_1, a_2` of the quartic, `z_2`, `d`,
`h`, `C`, `\mathcal{X}`. What stays is the notation a reader carries from one
page to the next.

## Expected size

Before merging the symbols several chapters share: Tides about 120 entries,
Thermalisation about 55, Inertial about 75, Active about 75, Droplets about 85.
Merging leaves roughly 330 rows in the full list, eight to ten pages. The short
list is nearer 130 rows and three to four pages. If your counts come out far
from these, something has been missed or over-included.

## Rules

- **Do not edit any file under `chapters/`.** Not one line. The chapters are
  finished and this work only reads them.
- The only files that change are the two new ones, `preamble.tex` and
  `main.tex`, and the two existing files gain lines rather than losing any.
- Bash is read only in this sandbox. Use `cat`, `sed -n`, `grep`, `awk`, `wc` to
  look, and never `>`, `>>`, `cp`, `mv`, `tee`, `sed -i` or a heredoc to write.
  A denied shell write can empty the target file first. Make every edit with the
  Write and Edit tools.
- Do not run `pdflatex`, `biber` or `python`. There is no TeX installation here.

## Verification before you report

1. Every symbol in your inventory appears in `symbols_full.tex`.
2. Every letter carrying two meanings has two adjacent rows naming different
   chapters. At least these do: `A`, `D`, `E`, `L`, `N`, `p`, `Q`, `T`,
   `\gamma`, `\lambda`, `\nu`, `m`, `u`.
3. Every symbol in the list still appears, by `grep`, in the chapter it is
   credited to. The rename moved many of them.
4. `symbols_short.tex` is a strict subset of `symbols_full.tex`, with identical
   wording for every row they share.
5. Both files use the same column widths and the same `longtable` header, so the
   two compile to the same shape.

Report the row count of each file, the symbols you judged ambiguous and why, and
anything in the chapters that looked wrong but which you did not touch.

## If you find a fault in a chapter

Do not fix it. Add it to `things_to_look_at.tex`, as a new item in the style of
the ones already there, and leave the chapter alone.
