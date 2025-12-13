# Archiving 400 GitHub Repos Locally: A Complete Backup Strategy

> **zzcollab blog post** | [Blog](https://example.com) | [Framework Documentation](https://github.com/rgt47/zzcollab)

## Overview

A comprehensive guide to backing up all your GitHub private repositories locally with verification, selective deletion, and complete metadata export. This reproducible blog post includes:

- Production-ready bash script (`github-archive.sh`)
- Three-phase backup/verify/delete workflow
- Dry-run mode for safety
- Complete metadata export (issues, PRs, releases, assets)
- Detailed step-by-step instructions

**Status**: Published
**License**: GPL-3
**Last Updated**: 2025-12-02

---

## Quick Start: Read the Blog Post

### View the Published Post

```bash
# The blog post is in analysis/paper/index.qmd
# Render it with Quarto:
quarto render analysis/paper/index.qmd

# Open in browser
open index.html
```

### Get the GitHub Archive Script

The complete production-ready script is embedded in the blog post.
To extract it:

```bash
# Copy the script section from analysis/paper/index.qmd
# Or download the script directly from the repository

chmod +x github-archive.sh
./github-archive.sh --help
```

### Prerequisites

- `gh` CLI installed and authenticated
- `git` installed
- Bash 4.0+
- Quarto (to render the blog post)

---

## Project Structure

This blog post follows the zzcollab/rrtools research compendium structure optimized for Quarto blog posts:

```
github_archive/
├── index.qmd               # Symlink to analysis/paper/index.qmd
├── figures/                # Symlink to analysis/figures/
├── media/                  # Symlink to analysis/media/
├── data/                   # Symlink to analysis/data/
│
├── analysis/
│   ├── paper/
│   │   ├── index.qmd       # Blog post content (MAIN FILE)
│   │   ├── figures/        # Symlink to ../figures/
│   │   ├── media/          # Symlink to ../media/
│   │   └── data/           # Symlink to ../data/
│   │
│   ├── figures/            # Generated visualizations (empty for this post)
│   ├── media/
│   │   ├── images/         # Hero images, screenshots
│   │   ├── audio/          # Podcasts, narration
│   │   └── video/          # Demos, tutorials
│   ├── scripts/            # Analysis scripts (optional)
│   └── data/               # Raw and derived data
│
├── R/                      # Reusable functions (optional)
├── tests/                  # Unit tests (optional)
├── DESCRIPTION             # Package metadata
├── Dockerfile              # Computational environment
├── renv.lock              # R package versions
└── Makefile               # Build automation
```

**Key**: Root-level symlinks enable Quarto compatibility while keeping actual content in `analysis/paper/` (rrtools convention).

---

## Development Workflow

### Editing the Blog Post

```bash
# 1. Edit the main blog post
vim analysis/paper/index.qmd

# 2. Preview changes
quarto preview analysis/paper/index.qmd

# 3. When satisfied, commit
git add .
git commit -m "Update blog post content"
git push
```

### Docker Workflow (Optional)

For development inside a container:

```bash
# 1. Build Docker image
make docker-build

# 2. Enter development environment
make docker-zsh

# 3. Install any additional dependencies needed
R
> install.packages("package-name")
> q()  # Auto-snapshots to renv.lock on exit

# 4. Render blog post in container
quarto render analysis/paper/index.qmd

# 5. Exit and commit
exit
git add .
git commit -m "Add/update dependencies"
```

### Common Tasks

```bash
quarto render analysis/paper/index.qmd      # Render blog post
quarto preview analysis/paper/index.qmd     # Live preview
make docker-build                           # Build Docker image
make docker-zsh                             # Start shell in container
make docker-rstudio                         # Start RStudio (localhost:8787)
make check-renv                             # Validate package dependencies
```

### Getting Help

The zzcollab framework has a comprehensive git-like help system:

```bash
# Brief overview
zzcollab                     # Show common workflows
zzcollab help                # Same

# Specific topics
zzcollab help quickstart     # Solo developer guide
zzcollab help workflow       # Daily development
zzcollab help team           # Team collaboration
zzcollab help config         # Configuration
zzcollab help docker         # Docker details
zzcollab help renv           # Package management

# List all topics
zzcollab help --all

# Legacy format (full options)
zzcollab --help
```

**Help Topics**:
- **Guides**: quickstart, workflow, team
- **Configuration**: config, profiles, examples
- **Technical**: docker, renv, cicd
- **Other**: options, troubleshoot

---

## Reproducibility

This project ensures reproducibility through five version-controlled components:

1. **Dockerfile** - Computational environment (R version, system dependencies)
2. **renv.lock** - Exact R package versions
3. **.Rprofile** - R session configuration
4. **Source code** - Analysis scripts and functions
5. **Data** - Raw and derived datasets

Any researcher can reproduce this analysis by:

```bash
git clone https://github.com/rgt47/githubarchive.git
cd githubarchive
zzcollab -u
make docker-zsh
# Analysis runs in identical environment
```

---

## Documentation

- **Analysis Data**: See `analysis/data/README.md` for data documentation
- **Development Guide**: See `docs/` for detailed technical documentation
- **zzcollab Framework**: See [zzcollab docs](https://github.com/rgt47/zzcollab)

---

## Citation

<!--
TODO: Add citation information here.
Example:

If you use this code or data, please cite:

Author, A. (2025). Title of Paper. *Journal Name*, volume(issue), pages.
DOI: 10.xxxx/xxxxx
-->

---

## License

This project is licensed under the GNU General Public License v3.0 (GPL-3).

### Summary

- ✅ You can use, modify, and distribute this code
- ✅ You must share modifications under GPL-3
- ✅ You must include license and copyright notice
- ❌ No warranty provided

**Full license**: See [LICENSE](LICENSE) file or https://www.gnu.org/licenses/gpl-3.0.en.html

---

## Contact

<!--
TODO: Add contact information
Example:

**Maintainer**: Your Name (your.email@example.com)
**Lab/Team**: [Team Name]
**Institution**: [Institution Name]
-->

---

## Acknowledgments

This research compendium was created using [zzcollab](https://github.com/rgt47/zzcollab),
a framework for reproducible computational research.

<!--
TODO: Add acknowledgments for funding, collaborators, data sources, etc.
-->
