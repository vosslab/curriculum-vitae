# Neil Voss curriculum vitae

Neil Voss's CV lives in small Markdown sections that are easy to read on GitHub and update independently. One build produces a typeset PDF and a structured DOCX for sharing, using locally bundled accessible fonts.

[Read the CV](https://vosslab.github.io/curriculum-vitae/) |
[View PDF](https://vosslab.github.io/curriculum-vitae/neil_voss_cv.pdf) |
[Download DOCX](https://vosslab.github.io/curriculum-vitae/neil_voss_cv.docx)

## Read or update the CV

Adding a paper starts in [cv/publications.md](cv/publications.md). Updating a software project
starts in [cv/software.md](cv/software.md). The Markdown files are the source of truth;
PDF and DOCX files are generated distribution copies.

| Section | Source |
| --- | --- |
| Contact information | [cv/profile.md](cv/profile.md) |
| Current position | [cv/current_position.md](cv/current_position.md) |
| Education | [cv/education.md](cv/education.md) |
| Research interests | [cv/research_interests.md](cv/research_interests.md) |
| Research appointments | [cv/research_appointments.md](cv/research_appointments.md) |
| Teaching experience | [cv/teaching.md](cv/teaching.md) |
| Faculty service | [cv/faculty_service.md](cv/faculty_service.md) |
| Software development and support | [cv/software.md](cv/software.md) |
| Research supervision | [cv/research_supervision.md](cv/research_supervision.md) |
| Honors | [cv/honors.md](cv/honors.md) |
| Grants and fellowships | [cv/grants.md](cv/grants.md) |
| Publications | [cv/publications.md](cv/publications.md) |
| Posters and presentations | [cv/presentations.md](cv/presentations.md) |
| Social media links | [cv/social_media.md](cv/social_media.md) |

## One source, several formats

- Simple headings, paragraphs, lists, and links are readable directly on GitHub.
- Yearly research-supervision lists become two columns in PDF and DOCX automatically.
- Atkinson Hyperlegible Next supplies the body text; Mono handles code and IBM Plex Sans
  Condensed handles long visible URLs. Font files are bundled and embedded in the documents.
- The DOCX retains headings, real lists, links, language metadata, and native columns.
  The PDF includes document structure tags. Accessibility checks and their limits are documented
  in [docs/VALIDATION.md](docs/VALIDATION.md).

<!-- screenshots:begin (managed by screenshot-docs) -->
<!-- screenshots:end -->

## Quick start

Use Bash, Python 3.12 or newer, Pandoc 3.1 or newer, and Pango. On macOS, the system tools can be
installed with `brew install pandoc pango`. On Debian/Ubuntu, use
`sudo apt-get install pandoc libpango-1.0-0 libpangoft2-1.0-0`.

```bash
source source_me.sh
python3 -m pip install -r pip_requirements.txt -r pip_requirements-dev.txt
python3 build_cv.py
```

The build writes these ignored files:

```text
output/pdf/neil_voss_cv.pdf
output/neil_voss_cv.docx
output/neil_voss_cv.html
output/CV.md
output/site/index.html
```

Open the PDF or DOCX to share it, or open the HTML for a local browser preview. Rebuild after
editing Markdown; changes made to generated files are overwritten. The build uses local assets
and does not read Google Docs or the original `raw/` exports.

## Add or change an entry

Follow the neighboring entry's plain Markdown format. For a student list, edit the relevant year
in [cv/research_supervision.md](cv/research_supervision.md):

```markdown
### 2027: 2 new students

- First student, master's
- Second student, undergrad
```

This example is illustrative, not CV content. A year heading and list are enough; the converter
supplies the columns. The GitHub view uses a normal single-column list.

[cv/sections.txt](cv/sections.txt) defines document order, one filename per line. When adding a
whole section, create its Markdown file and add its filename there. The build rejects missing,
duplicated, or unlisted sections. Keep layout changes in [styles/cv.css](styles/cv.css) and
[build_cv.py](build_cv.py).

## Checks and downloads

```bash
source source_me.sh && python3 -m pytest tests/ --no-ascii-fix
```

The included GitHub Actions workflow runs the checks and builds PDF/DOCX artifacts after a push.
After a successful run, download the `neil-voss-cv` artifact from the repository's Actions tab.
Successful builds on `main` also deploy the HTML CV, PDF, and DOCX to GitHub Pages.
Pull requests build and test without publishing. Generated files are never committed.

For initial setup, open repository **Settings > Pages** and select **GitHub Actions** as the
build source. Commit and push the workflow and source changes to `main`, then watch the
`documents` and `deploy` jobs in **Actions > Build CV**. Later pushes update the same public URLs.
The Pages steps follow the starter-repo-template deployment workflow, using the existing Python
build instead of an additional Node build.

To preview the exact site locally after a build:

```bash
source source_me.sh && python3 -m http.server 8000 --directory output/site
```

Open `http://localhost:8000/`. Only the staged `output/site/` directory is published, including
bundled fonts and their license notices; original exports and QA files are excluded.

## Maintenance notes

- [docs/VALIDATION.md](docs/VALIDATION.md): local validation evidence and compatibility limits.
- [docs/DESIGN_DECISIONS.md](docs/DESIGN_DECISIONS.md): source and publishing decisions.
- [docs/HUMAN_GUIDANCE.md](docs/HUMAN_GUIDANCE.md): author instructions and future software updates.
- [docs/CHANGELOG.md](docs/CHANGELOG.md): repository changes.
- [assets/fonts/README.md](assets/fonts/README.md): font sources, licenses, and checksums.

## License

Source code: [LICENSE.MIT](LICENSE.MIT).

Documentation and other non-code materials: [LICENSE.CC-BY-4.0](LICENSE.CC-BY-4.0).

Bundled fonts retain their own SIL Open Font License notices, described in
[assets/fonts/README.md](assets/fonts/README.md), with the complete license in
[LICENSE.OFL-1.1](LICENSE.OFL-1.1).
