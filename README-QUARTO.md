# Build this book with Quarto

This repository contains the manuscript files for "The Developer's Playbook" and a minimal Quarto configuration to render them as a static book.

Prerequisites
- Install Quarto: https://quarto.org/docs/get-started/
- (Optional) Install Pandoc if your system doesn't already have it (Quarto bundles it in most installs).

Render the book locally

Open PowerShell in the repository root (where `_quarto.yml` is located) and run:

```powershell
quarto render
quarto preview  # optional: runs a local web server and watches for changes
```

Output
- The rendered site will be in the `_site` folder by default.

Customization
- To change chapter order, edit `_quarto.yml` and modify the `book.chapters` list.
- To use `.qmd` files for advanced features (executable code, callouts, etc.) you can rename the `.md` files to `.qmd` and update the `_quarto.yml` accordingly.

Problems or questions? Tell me what output you see and I can help fix build issues.
