# Thesis Source Formatting / Merge Map

Last updated: 2026-04-26

## Scope

- Core chapter-source papers: `cellprobe`, `hardest`, `lop`, `lossy`, `randomstrings`, `totalfuncs`
- Supplemental source paper: `survey`
- Status note: `totalfuncs` is currently empty

## Paper Inventory

### `cellprobe`

- Title: `Stronger Cell Probe Lower Bounds via Local PRGs`
- Entry `.tex`: [`papers/cellprobe/Cell.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/cellprobe/Cell.tex)
- Bibliography file: [`papers/cellprobe/Cell.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/cellprobe/Cell.bib)
- Bibliography style in source: `alpha`
- Figure assets detected: none
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - defines a large local macro block
  - defines many theorem-like environments, including `claim`, `problem`, `assumption`, `goal`
  - loads `natbib` twice in the preamble

### `hardest`

- Title: `The Hardest Explicit Construction`
- Entry `.tex`: [`papers/hardest/apepp.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/hardest/apepp.tex)
- Bibliography file: [`papers/hardest/apepp.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/hardest/apepp.bib)
- Bibliography style in source: `siam`
- Figure assets detected:
  - [`papers/hardest/circuit_tree.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/hardest/circuit_tree.pdf)
  - [`papers/hardest/efficient_circuit_landscape.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/hardest/efficient_circuit_landscape.pdf)
  - [`papers/hardest/Non_Rigid_Circuit.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/hardest/Non_Rigid_Circuit.pdf)
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - relatively compact theorem/macro block
  - shares a common style family with `lossy`, `lop`, and parts of `survey`

### `lop`

- Title: `Strong vs. Weak Range Avoidance and the Linear Ordering Principle`
- Entry `.tex`: [`papers/lop/main.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/lop/main.tex)
- Bibliography file: [`papers/lop/Missing.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/lop/Missing.bib)
- Bibliography style in source: `alpha`
- Figure assets detected:
  - [`papers/lop/Classes.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lop/Classes.pdf)
  - [`papers/lop/Lop_tree.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lop/Lop_tree.pdf)
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - defines `stmaryrd`
  - loads `natbib` twice in the preamble
  - portability warning: source calls `classes.pdf`, but the file on disk is `Classes.pdf`

### `lossy`

- Title: `Derandomization from Time-Space Tradeoffs`
- Entry `.tex`: [`papers/lossy/space.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/space.tex)
- Bibliography file: [`papers/lossy/space.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/space.bib)
- Bibliography style in source: `alpha`
- Figure assets detected:
  - [`papers/lossy/space_results_table.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/space_results_table.pdf)
  - [`papers/lossy/php_bpp_picture.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/php_bpp_picture.pdf)
  - [`papers/lossy/j-tree.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/j-tree.pdf)
  - [`papers/lossy/write_operation_forward.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/write_operation_forward.pdf)
  - [`papers/lossy/write_operation_backwards.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/write_operation_backwards.pdf)
  - [`papers/lossy/simulation.pdf`](/Users/oliverkorten/Documents/Codex/thesis/papers/lossy/simulation.pdf)
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - adds `caption`, `multirow`, and `algorithm2e`
  - defines theorem-like environments similar to `hardest`

### `randomstrings`

- Title: `How to Construct Random Strings`
- Entry `.tex`: [`papers/randomstrings/main.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/randomstrings/main.tex)
- Bibliography file: [`papers/randomstrings/ref.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/randomstrings/ref.bib)
- Bibliography style in source: `alphaurl`
- Figure assets detected: none
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - preamble diverges most from the other papers
  - uses a larger package stack including `tikz`, `xy`, `cleveref`, `complexity`, `listings`, `titlesec`, `sectsty`, `subfigure`
  - defines its own notation family such as `\Recon`, `\SH`, `\WH`, `\DLOGTIME`

### `survey`

- Title: `Range Avoidance and the Complexity of Explicit Constructions`
- Entry `.tex`: [`papers/survey/main.tex`](/Users/oliverkorten/Documents/Codex/thesis/papers/survey/main.tex)
- Bibliography file: [`papers/survey/Survey.bib`](/Users/oliverkorten/Documents/Codex/thesis/papers/survey/Survey.bib)
- Bibliography style in source: `alpha`
- Figure assets detected: none
- Source shape:
  - standalone `article`
  - self-contained preamble
  - no `\input{...}` / `\include{...}` detected
- Merge notes:
  - should be treated as a reusable source bank, not a chapter source by default
  - loads `natbib` twice in the preamble
  - reuses some conventions seen in `cellprobe` and `lop`

### `totalfuncs`

- Status: no source files loaded yet

## Cross-Paper Formatting Picture

### Shared structure

- Every loaded paper is currently a standalone `article`
- Every loaded paper is self-contained rather than split across multiple included `.tex` files
- Every loaded paper currently uses a local bibliography file
- The main figure assets are all `.pdf`

### Bibliography differences to reconcile later

- `cellprobe`, `lop`, `lossy`, `survey`: `alpha`
- `randomstrings`: `alphaurl`
- `hardest`: `siam`

Thesis merge implication:

- the thesis should eventually use one bibliography backend and one house style
- we should plan on merging bibliography entries into a single thesis-level `.bib`

### Preamble / package differences to reconcile later

- Common package family across most papers:
  - `geometry`, `enumitem`, `bm`, `amsfonts`, `amsmath`, `xcolor`, `graphicx`, `amsthm`, `hyperref`
- Repeated special-purpose packages across several papers:
  - `qtree`, `tree-dvips`, `float`, `authblk`
- Paper-specific extras:
  - `lossy`: `caption`, `multirow`, `algorithm2e`
  - `lop`: `bbm`, `stmaryrd`
  - `cellprobe`: `bbm`
  - `randomstrings`: `graphics`, `mathtools`, `sectsty`, `titlesec`, `subfigure`, `color`, `verbatim`, `babel`, `xspace`, `mathrsfs`, `bbm`, `xy`, `tabularx`, `array`, `listings`, `url`, `tikz`, `cleveref`, `complexity`

Thesis merge implication:

- we should not import paper preambles directly into thesis chapters
- instead, we should build one thesis-level preamble and one thesis-level macro file
- chapter files should eventually contain body content only

### Theorem environment differences to reconcile later

- Common core environments across many papers:
  - `theorem`, `lemma`, `definition`, `corollary`, `proposition`, `observation`
- Additional environments appear selectively:
  - `cellprobe`: `claim`, `conjecture`, `hypothesis`, `problem`, `assumption`, `goal`
  - `survey`: `claim`, `conjecture`, `hypothesis`, `problem`
  - `lossy`: `conjecture`, `hypothesis`
  - `randomstrings`: `conjecture`, `hypothesis`

Thesis merge implication:

- the thesis needs one canonical theorem setup
- we should decide later whether numbering is global-by-chapter or tied to section/chapter style required by your university template

### Macro overlap to reconcile later

- Repeated across multiple papers:
  - `\todo`, `\note`, `\dash`, `\B`, `\poly`
- Repeated in some papers with overlapping meaning:
  - `\rng`
- Paper-specific notation families:
  - `cellprobe`: entropy / rank / local-PRG notation
  - `hardest`: explicit-construction bounds such as `\varbound`, `\ttbound`
  - `lop`: range-avoidance notation such as `\dom`, `\corng`, `\nodes`
  - `lossy`: concatenation notation `\cat`, plus proof-system notation
  - `randomstrings`: random-string and circuit-class notation
  - `survey`: explicit-construction survey notation such as `\ec`, `\avoid`, `\lossy`

Thesis merge implication:

- we should create one thesis macro file for canonical notation
- before body merging, we should make a notation decision sheet so conflicting names are resolved once

## Immediate Risks / Cleanup Items

- `lop/main.tex` references `classes.pdf`, but the file currently present is `Classes.pdf`
- `cellprobe/Cell.tex`, `lop/main.tex`, and `survey/main.tex` each load `natbib` twice
- macOS metadata file present:
  - [`papers/.DS_Store`](/Users/oliverkorten/Documents/Codex/thesis/papers/.DS_Store)

## Recommended Merge Strategy

1. Wait for `totalfuncs` source files.
2. Create a thesis-level skeleton with:
   - one master `main.tex`
   - one thesis preamble
   - one macros file
   - one combined bibliography file
3. Create a notation decision note before importing chapter bodies.
4. Convert each paper into a body-only chapter source:
   - remove standalone preamble
   - point figures to stable thesis paths or preserve per-paper figure folders
   - replace local bibliography commands with thesis-level bibliography management
5. Treat `survey` as a reference reservoir for introduction/background only.
