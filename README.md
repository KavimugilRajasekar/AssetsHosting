# AssetsHosting

A public asset bucket for serving resume, reports, and brand assets through GitHub's raw CDN.

![Language](https://img.shields.io/badge/language-Markdown-blue)
![Topic](https://img.shields.io/badge/topic-assets-informational)
![Topic](https://img.shields.io/badge/topic-resume-informational)
![Topic](https://img.shields.io/badge/topic-pdf-informational)
![License](https://img.shields.io/badge/license-see_repo-lightgrey)

---

## Overview

AssetsHosting is a lightweight, GitHub-Pages-friendly asset bucket that hosts public documents and brand media as static files. It is intentionally minimal: no build step, no runtime, no backend. Everything is served as-is through GitHub's raw content CDN so that other projects, recruiters, and applications can resolve stable, version-controlled URLs to the resume, academic reports, and brand logo.

## Why This Project Exists

When an applicant or a developer needs to reference the same resume or the same brand logo from many places (portfolio sites, GitHub READMEs, third-party apps), they need a stable, public source of truth. This repository serves that role. By keeping resume, summary essay, ML assignment report, and the personal brand logo in a single version-controlled bucket, every consumer can deep-link to canonical URLs that never silently change location or disappear.

## Table of Contents

- [Overview](#overview)
- [Why This Project Exists](#why-this-project-exists)
- [Banner](#banner)
- [Key Features](#key-features)
- [Architecture Overview](#architecture-overview)
- [Tech Stack](#tech-stack)
- [Folder Structure](#folder-structure)
- [Installation / Setup](#installation--setup)
- [Usage / Examples](#usage--examples)
- [Configuration](#configuration)
- [Learning Outcomes](#learning-outcomes)
- [Challenges Faced](#challenges-faced)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

## Key Features

- Static, public asset hosting with no server runtime
- Resume distributed as PDF for consistent rendering across devices
- Academic deliverables (ML assignment report, summary essay) available as DOCX
- Brand logo available as a high-resolution PNG
- Stable, deep-linkable URLs via GitHub raw content CDN
- Zero build pipeline, zero configuration
- Version-controlled content using a normal Git workflow
- Suitable for consumption from portfolio sites, GitHub profiles, and external apps

## Architecture Overview

The repository follows the simplest possible architecture: a flat, public collection of binary and document files served directly through GitHub's raw content endpoint. There is no API, no authentication layer, and no transformation pipeline.

- **Raw CDN layer** — GitHub serves files at `raw.githubusercontent.com/...` paths
- **Document layer** — PDF for resume, DOCX for narrative reports, PNG for brand assets
- **Discovery layer** — This README documents canonical asset paths and usage notes

## Tech Stack

| Area | Technology |
|------|------------|
| Hosting | GitHub Pages / Raw CDN |
| Document formats | PDF, DOCX |
| Image formats | PNG |
| Documentation | Markdown |
| Version control | Git |
| Build pipeline | None |

## Folder Structure

```text
AssetsHosting/
├── README.md
├── logo.png
├── Kavimugil_Rajasekar_Resume.pdf
├── ML Assignment-1 Report.docx
├── SummaryEssay.docx
└── screenshots/
    └── logo.png
```

## Installation / Setup

There is nothing to install. Clone the repository if you want a local copy:

```bash
git clone https://github.com/KavimugilRajasekar/AssetsHosting.git
```

Or simply resolve a file over HTTP from GitHub's raw CDN.

## Usage / Examples

Reference any asset from a Markdown file or HTML page:

```markdown
![Brand Logo](https://raw.githubusercontent.com/KavimugilRajasekar/AssetsHosting/main/logo.png)
```

Embed the resume as a downloadable link:

```markdown
[Download Resume (PDF)](https://raw.githubusercontent.com/KavimugilRajasekar/AssetsHosting/main/Kavimugil_Rajasekar_Resume.pdf)
```

Reference the summary essay from a course platform or a personal site:

```markdown
[Summary Essay (DOCX)](https://raw.githubusercontent.com/KavimugilRajasekar/AssetsHosting/main/SummaryEssay.docx)
```

Reference the ML assignment report:

```markdown
[ML Assignment 1 Report (DOCX)](https://raw.githubusercontent.com/KavimugilRajasekar/AssetsHosting/main/ML%20Assignment-1%20Report.docx)
```

## Configuration

No configuration is required. If you fork this repository to host your own assets:

- Replace `logo.png` with your own brand logo
- Replace the resume PDF with your own (keep the same filename or update the URL references)
- Update the links in any consumers that point back to this bucket

## Learning Outcomes

- Understanding of static asset hosting through GitHub raw content
- Awareness of URL design for stable, shareable, version-controlled assets
- Practical experience with binary files in Git and Markdown-driven documentation
- Clean separation between content (documents) and presentation (consumer sites)

## Challenges Faced

- Filenames that contain spaces (such as `ML Assignment-1 Report.docx`) require URL-encoded consumers
- GitHub's raw content URL is case-sensitive and branch-dependent, so consumers must agree on the branch name
- Large binary files increase clone size for anyone who pulls the entire repository
- Docx rendering depends on the consumer's local tooling and is not always previewable in browsers

## Future Improvements

- Add a `CNAME` or GitHub Pages config so the bucket can be served from a custom domain
- Publish a manifest file (`assets.json`) describing each asset and its canonical URL
- Mirror critical assets in a second CDN for redundancy
- Provide Markdown-friendly cover thumbnails for each document

## Contributing

This repository is a personal asset bucket, but suggestions are welcome:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Open a pull request describing the improvement

Do not submit personal documents to a fork that you intend to publish — keep personal content in personal forks.

## License

This repository does not include a `LICENSE` file. The resume and academic reports are personal documents belonging to the author and are not licensed for redistribution. The brand logo may be used to reference the author's portfolio with attribution.

## Author

**Kavimugil Rajasekar**

- Portfolio: [https://KavimugilRajasekar.github.io](https://KavimugilRajasekar.github.io)
- GitHub: [https://github.com/KavimugilRajasekar](https://github.com/KavimugilRajasekar)