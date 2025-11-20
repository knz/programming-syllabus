# Intro Programming Syllabus

This repository contains an introductory programming syllabus and
accompanying notes written in reStructuredText and typeset via LaTeX.

The material is organized into short, self-contained documents
(e.g. variables, control flow, arrays, recursion) that can be built
into HTML, PDF, and plain-text formats.

## Repository layout

- `src/` – reStructuredText (`.rst`) sources for each topic, plus `index-header.rst` used to generate the top-level index.
- `aux/` – LaTeX base style, Pygments style, and the LaTeX template used when producing PDFs.
- `build/` – build directory containing the `Makefile` and all generated artifacts (`*.pdf`, `*.html`, `*.txt`, logs, etc.).

The main list of documents and build rules live in `build/Makefile`.

## Prerequisites

To build the syllabus you will need:

- A LaTeX distribution with `latexmk` available on your `PATH` (e.g. TeX Live).
- Python tools from Docutils providing `rst2html` and `rst2latex` (often available via a package like `python3-docutils`).
- A standard POSIX shell environment with common utilities (`grep`, `head`, etc.).

On Debian/Ubuntu-like systems, the following packages are typically sufficient (names may vary):

- `texlive` (and related `latexmk` package, if separate)
- `python3-docutils`

## Building the documents

All build commands are run from the `build/` directory.

### Build everything

```bash
cd build
make
```

This will generate, for each document listed in `DOCS` in `build/Makefile`:

- `NAME.txt` – a copy of the source `.rst` file
- `NAME.html` – HTML version
- `NAME.pdf` – PDF version

It will also generate `index.html` and `index.txt`, which provide an index page linking to each topic in all available formats.

### Clean up build artifacts

From within `build/`:

```bash
# Remove logs and LaTeX aux files
make prune

# Remove all generated PDFs, HTML, and text files (includes prune)
make clean
```

