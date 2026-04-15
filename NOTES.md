# Real Analysis Notes

This repository is a collection of self-contained HTML notes on real analysis. Each note explains a concept with formal definitions, proofs, worked examples, and interactive visualizations — all rendered in the browser with no build step.

## Audience

- The primary reader is the repo author studying real analysis.
- AI agents use this file as the authoritative guide when generating or editing notes.

## Repository Structure

```
real-analysis/
  NOTES.md                   # this file — repo purpose and conventions
  index.html                 # table of contents linking to every note
  styles/
    main.css                 # shared stylesheet for all notes
  templates/
    note-template.html       # skeleton to copy when creating a new note
  notes/
    <topic-slug>.html        # one file per concept
```

## Note Structure

Every note is a standalone HTML file in `notes/`. Each note must contain the following sections in order:

### 1. Title and Metadata

- The `<title>` and a visible `<h1>` with the concept name.
- A metadata block listing: **topic area** (e.g., sequences, continuity, integration).

### 2. Motivation / Intuition

A plain-language section answering *"Why does this concept matter?"* and *"What problem does it solve?"*. No formal notation required — the goal is to build intuition before diving into rigor.

### 3. Formal Definitions

Precise mathematical statements rendered with LaTeX via KaTeX. Each definition should be wrapped in a styled `<div class="definition">` block with a label (e.g., "Definition 3.1").

### 4. Key Theorems and Proofs

Statement–proof pairs. Theorems go in `<div class="theorem">` blocks; proofs go in `<div class="proof">` blocks ending with a tombstone (∎). Include proof sketches when a full proof is too long, and link to a reference for the complete argument.

### 5. Visualizations

Interactive or static visual aids that illuminate the concept. Examples:

- Epsilon-delta diagrams with draggable sliders.
- Animated sequence convergence plots.
- Highlighted regions for Riemann sums.

Implementation rules:

- Use plain JavaScript with `<canvas>` or inline `<svg>`.
- No external JS frameworks (React, D3, etc.).
- Wrap each visualization in a `<figure>` with a `<figcaption>`.
- Provide meaningful defaults so the visualization is useful without interaction.

### 6. Worked Examples

Concrete calculations or constructions that apply the definitions and theorems. Each example lives in a `<div class="example">` block.

### 7. Exercises

Practice problems for the reader. Optionally include solutions hidden behind a `<details>` / `<summary>` toggle. Wrap each exercise in a `<div class="exercise">` block.


## Tech Conventions

| Concern | Convention |
|---|---|
| Math rendering | KaTeX via CDN (`https://cdn.jsdelivr.net/npm/katex/dist/`) with auto-render extension |
| Styling | Shared `../styles/main.css` linked from every note |
| Visualizations | Plain JS + `<canvas>` or inline SVG — no heavy frameworks |
| File naming | `notes/<topic-slug>.html` (lowercase, hyphens, no spaces) |
| HTML standard | HTML5, UTF-8, responsive viewport meta tag |

## Adding a New Note (AI Agent Instructions)

When asked to create a new note, follow these steps exactly:

1. **Copy the template.** Duplicate `templates/note-template.html` to `notes/<topic-slug>.html`.
2. **Fill every section.** Replace all placeholder content. Do not leave `TODO` markers in the final file.
3. **Write at least one visualization.** Every note must include at least one interactive or static diagram in section 5.
4. **Update the index.** Add an `<li>` entry for the new note in `index.html` under the appropriate topic group.
5. **Check links.** If the note has prerequisites, verify those note files exist and link to them.
6. **Validate.** Ensure the HTML is well-formed and the page renders correctly when opened directly in a browser (no server required).


