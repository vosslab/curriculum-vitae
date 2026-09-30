## 2026-09-30

### CV publishing

- Updated the GitHub Actions runner to Ubuntu 26.04 after checking hosted-runner and Python 3.12
  availability. Retained push, pull-request, and manual build triggers.
- Recorded the monochrome PDF/DOCX preference, with dark blue links as the only color;
  aligned the DOCX long-URL style with the existing dark blue hyperlink style.
- Migrated the supplied CV into 14 independently editable GFM sections, preserving its factual
  content and adding the author's five supplied social profile links.
- Added one local build command for PDF, structured DOCX, HTML preview, and assembled Markdown.
- Added automatic two-column supervision lists, consistent typography, bundled fonts, and document
  font embedding. Kept layout details out of the Markdown sources.
- Added conversion tests, a GitHub Actions artifact build, and a README section index and build guide.
- Verified source text preservation, bundled-font PDF rendering, DOCX rendering in LibreOffice,
  responsive browser previews, and 110 passing repository/conversion checks.

### Fixes and Maintenance

- Synchronized shared style guides, tests, and repository support files from the starter template.
