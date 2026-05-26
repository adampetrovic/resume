Adam Petrovic's resume built with LaTeX.

## Building

### Docker

Recommended, because it includes the required LaTeX packages:

```bash
docker run --rm --platform linux/amd64 \
  -v "$PWD":/workdir \
  -w /workdir \
  ghcr.io/xu-cheng/texlive-full:latest \
  pdflatex -interaction=nonstopmode resume.tex
```

This writes `resume.pdf` in the repository root.

On Apple Silicon, keep `--platform linux/amd64`; the image does not currently publish an arm64 manifest.

### Local LaTeX

If you have a local LaTeX distribution with Lato and FontAwesome installed:

```bash
pdflatex -interaction=nonstopmode resume.tex
```

## Automated Releases

This repository automatically generates and releases the resume PDF using GitHub Actions:

- **Trigger**: Pull requests compile the PDF; pushes to `master` or manual workflow dispatch also compile and release
- **Output**: Date-stamped release (e.g., `resume-2025-07-25`) with attached PDF on `master`
- **Location**: Check the [Releases](../../releases) page for the latest version

The workflow compiles the LaTeX source using pdflatex and creates a new release with the generated PDF attached.

## Files

- `resume.tex` - LaTeX source file
- `resume.pdf` - Generated PDF (updated by GitHub Actions)
- `.github/workflows/release.yml` - Automated build and release workflow
