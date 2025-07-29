# Research Snippets

A structured repository for research thoughts, experiments, and LaTeX documents.

## Structure

```
research-snippets/
├── README.md               ← what the repo is for, how to build
├── .gitignore              ← ignore LaTeX aux files, PDFs, Python cache
│
├── notes/                  ← raw thoughts & explorations
│   ├── 2025-07-29-*.md    ← dated notes and ideas
│   ├── Makefile           ← build utilities
│   └── *.ipynb            ← analysis notebooks
│
├── drafts/                 ← one sub-dir per paper/report
│   └── main-paper/
│        ├── main.tex       ← master file
│        ├── tex/          ← sections: \input{tex/intro.tex} …
│        ├── figs/         ← figures and images
│        ├── bib/          ← bibliography files
│        └── Makefile      ← latexmk build rules
│
├── code/                   ← analysis scripts, notebooks
│   ├── requirements.txt   ← Python dependencies
│   └── *.py               ← analysis scripts
│
└── templates/              ← shared .cls/.sty, styles, etc.
```

## Building Documents

### Individual Papers

Navigate to any draft directory and run:

```bash
cd drafts/main-paper/
make pdf          # Build PDF
make clean        # Clean auxiliary files
make watch        # Build continuously on file changes
make open         # Open PDF after building
```

### Requirements

- **LaTeX**: A complete LaTeX distribution (TeX Live, MiKTeX, etc.)
- **latexmk**: For automated builds (usually included with LaTeX)
- **Python** (optional): For analysis scripts in `code/`

## Usage Guidelines

| Folder | Purpose | Git Strategy |
|--------|---------|--------------|
| **notes/** | Daily thoughts, meeting minutes, brainstorming | Commit often, use dated filenames |
| **drafts/** | Serious write-ups, each in its own directory | Only commit source files, never PDFs |
| **code/** | Data analysis, figure generation | Pin dependencies, document usage |
| **templates/** | Shared styles, classes, formatting | Rarely changes, keeps repo self-contained |

## Git Best Practices

- **Auxiliary files**: Already ignored in `.gitignore`
- **PDFs**: Never committed (build artifacts only)
- **Commits**: Use atomic, descriptive messages
- **Branches**: Use feature branches for major rewrites

## Getting Started

1. Add your thoughts to `notes/` with dated filenames
2. Create new paper directories in `drafts/` when ready
3. Use `code/` for any analysis that feeds into papers
4. Keep `templates/` for shared formatting resources

Happy writing! 🎓