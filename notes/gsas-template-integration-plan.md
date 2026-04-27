# GSAS Template Integration Plan

Last updated: 2026-04-27

## Decision

The thesis manuscript should follow the Columbia GSAS LaTeX template located in:

- [`GSAS Template/`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template)

Going forward, this template is the governing formatting baseline for the dissertation.

## What In The Template Matters

### Main entry point

- Template root file: [`GSAS Template/thesis.tex`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/thesis.tex)

### Front matter structure

The template expects dedicated files for:

- title page
- copyright page
- abstract
- acknowledgements
- dedication
- preface
- conclusion
- appendix

These are provided as separate `.tex` files in the template folder.

### Formatting conventions currently encoded

- `report` class at `12pt`
- 1 inch margins on all sides
- double spacing by default
- Times-style text font
- custom chapter / TOC formatting via `titlesec` and `tocloft`
- bibliography handled with `biblatex` using `backend=bibtex`
- bibliography printed as a chapter-level `References` section
- Roman numeral page numbering for front matter
- Arabic numbering reset for the main body

## Immediate Consequences For Our Existing Thesis Skeleton

Our current scaffold in [`thesis-body/`](/Users/oliverkorten/Documents/Codex/thesis/thesis-body) is still useful as a content-organizing draft area, but it is not yet GSAS-compliant.

In particular, it differs from the template on:

- font size: `11pt` vs GSAS `12pt`
- spacing: not currently double-spaced by default
- bibliography system: `natbib` vs GSAS `biblatex`
- front matter structure: currently too minimal
- chapter / TOC styling: generic rather than GSAS template styling

## Short-Term Plan

1. Treat the GSAS template as the thesis shell from now on.
2. Preserve `papers/` unchanged as source material.
3. Preserve `notes/` as planning / notation / merge documentation.
4. Migrate thesis manuscript work from the generic scaffold into a GSAS-based manuscript area.
5. Rebuild the thesis-level shared preamble and macro setup inside the GSAS-based root, not inside the old generic root.
6. Only after that, start importing the first paper as a body-only chapter.

## Recommended Implementation Path

### Phase 1: Establish GSAS-based master manuscript

- create a working dissertation root derived from the GSAS template
- keep template formatting conventions intact unless a mathematical need requires an addition
- wire VS Code / LaTeX Workshop to compile the GSAS-based root file

### Phase 2: Add shared math infrastructure

- add a thesis macros file for notation
- add theorem environments needed for complexity theory content
- keep these additions modular so the underlying GSAS structure stays recognizable

### Phase 3: Move chapter organization over

- create chapter files corresponding to the thesis plan
- map your six core papers onto chapter slots
- treat the survey as a source reservoir for introduction/background only

### Phase 4: Merge references

- replace sample bibliography data with a thesis bibliography
- merge entries from paper-level `.bib` files into a dissertation-level `.bib`
- preserve GSAS bibliography workflow while deciding on any style adjustments only if necessary

## File-Level Observations

- [`GSAS Template/thesis.tex`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/thesis.tex) is the operative template file
- [`GSAS Template/GSAS Dissertation Template Latex Instructions.txt`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/GSAS%20Dissertation%20Template%20Latex%20Instructions.txt) confirms the intended compile order and customization flow
- [`GSAS Template/references.bib`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/references.bib) is placeholder sample data only
- [`GSAS Template/thesis-blx.bib`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/thesis-blx.bib) is generated auxiliary metadata, not source content
- [`GSAS Template/approvalPage.tex`](/Users/oliverkorten/Documents/Codex/thesis/GSAS%20Template/approvalPage.tex) appears present but is not currently included by `thesis.tex`

## Practical Rule Going Forward

When there is tension between:

- our generic thesis scaffold, and
- the GSAS template

the GSAS template should win unless there is a clear dissertation-specific mathematical requirement that forces an extension.
