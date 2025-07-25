Adam Petrovic's resume built with LaTeX.

## Building

To compile the resume PDF locally:

```bash
xelatex resume.tex
```

## Automated Releases

This repository automatically generates and releases the resume PDF using GitHub Actions:

- **Trigger**: Pushes to the `master` branch or manual workflow dispatch
- **Output**: Date-stamped release (e.g., `resume-2025-07-25`) with attached PDF
- **Location**: Check the [Releases](../../releases) page for the latest version

The workflow compiles the LaTeX source using XeLaTeX and creates a new release with the generated PDF attached.

## Files

- `resume.tex` - LaTeX source file
- `resume.pdf` - Generated PDF (updated by GitHub Actions)
- `.github/workflows/release.yml` - Automated build and release workflow
