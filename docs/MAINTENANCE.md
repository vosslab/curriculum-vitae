# Maintaining and publishing the CV

## One source, several formats

- Simple headings, paragraphs, lists, and links are readable directly on GitHub.
- Yearly research-supervision lists become two columns in PDF and DOCX automatically.
- Atkinson Hyperlegible Next supplies the body text; Mono handles code and IBM Plex Sans
  Condensed handles long visible URLs. Font files are bundled and embedded in the documents.
- The DOCX retains headings, real lists, links, language metadata, and native columns.
  The PDF includes document structure tags. Accessibility checks and their limits are documented
  in [VALIDATION.md](VALIDATION.md).

## Quick start

Use Bash, Python 3.12 or newer, Pandoc 3.1 or newer, and Pango. On macOS, the system tools can be
installed with `brew install pandoc pango`. On Debian/Ubuntu, use
`sudo apt-get install pandoc libpango-1.0-0 libpangoft2-1.0-0 libharfbuzz-subset0`.

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
in [../cv/research_supervision.md](../cv/research_supervision.md):

```markdown
### 2027: 2 new students

- First student, master's
- Second student, undergrad
```

This example is illustrative, not CV content. A year heading and list are enough; the converter
supplies the columns. The GitHub view uses a normal single-column list.

[../cv/sections.txt](../cv/sections.txt) defines document order, one filename per line. When adding a
whole section, create its Markdown file and add its filename there. The build rejects missing,
duplicated, or unlisted sections. Keep layout changes in [../styles/cv.css](../styles/cv.css) and
[../build_cv.py](../build_cv.py).

## Checks and downloads

```bash
source source_me.sh && python3 -m pytest tests/ --no-ascii-fix
```

The included GitHub Actions workflow checks CV sources and conversion before building documents.
Non-CV documentation checks run independently: their failures remain visible but do not block
publication of a valid CV. The full local test command above still checks everything.
Download the optional `neil-voss-cv` artifact from the repository's Actions tab when its upload
succeeds. Successful builds and required Pages artifact uploads on `main` deploy the HTML CV,
PDF, and DOCX to GitHub Pages even if the optional download upload fails.
Pull requests build and test without publishing. Generated files are never committed.

Package downloads have bounded retries, and jobs have time limits. Runs for the same branch are
serialized; active deployments finish before the next deployment starts. Build failures prevent
deployment, preserving the previously published site. After an infrastructure failure, use the
Actions rerun control; validation failures require correcting the source.

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

- [CITATION_STYLE.md](CITATION_STYLE.md): NLM format, byline sources, and remaining metadata gaps.
- [VALIDATION.md](VALIDATION.md): local validation evidence and compatibility limits.
- [DESIGN_DECISIONS.md](DESIGN_DECISIONS.md): source and publishing decisions.
- [HUMAN_GUIDANCE.md](HUMAN_GUIDANCE.md): author instructions and future software updates.
- [CHANGELOG.md](CHANGELOG.md): repository changes.
- [../assets/fonts/README.md](../assets/fonts/README.md): font sources, licenses, and checksums.


Return to [../README.md](../README.md) for the academic overview and CV downloads.
