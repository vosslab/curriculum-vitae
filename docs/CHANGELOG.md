## 2026-09-30

### CV publishing

- Confirmed that the WoS-indexed cryo-EM gateway grant is existing NSF award 1759735;
  added the NSF-verified PI designation and saved the official award response locally.

- Recorded the author-confirmed 32-73 citation bounds for the two missing per-paper counts
  and the recalled possible WoS duplicate; kept dashboard metrics explicitly source-reported.

- Updated the CV to the supplied September 30, 2026 WoS profile metrics (2,961 citations,
  h-index 17); preserved 21 deduplicated per-work counts and documented missing counts,
  correction-record handling, and the distinction between references and citations.

- Moved PDF/DOCX footers inside the 0.6-inch printable boundary and reserved a separate
  0.25-inch footer band above it, retaining 0.6-inch top and side margins.

- Completed source reconciliation: merged publication duplicates, added all supplied identifiers,
  corrected citation details and physics metadata, retained the erratum, separated the unpublished
  manuscript, and incorporated organizational units. Updated audits to distinguish completed work
  from unresolved personal-history facts.

- Audited the saved ORCID print view against all CV sections; documented full work coverage,
  missing DOI fields, additional appointment detail, and conflicting dates without changing CV facts.

- Saved the supplied physics-paper ORCID records locally and in the publication audit; added
  both DOIs to the CV and documented unresolved initials and volume differences.

- Added the author-supplied ORCID URL to the CV contact information.

- Reconciled the 2001 protein-atom types citation with PMID 11673240, including Voss N and
  Gerstein M, its DOI, and publication month; resolved both unmatched biomedical records.

- Reconciled the 2000 RNA base-pair database citation with the author-supplied PMID 10592279:
  indexed author initials, publication date, DOI, PMID, and PMCID.

- Replaced the fixed 2023 Last Modified line with the current America/Chicago build date in
  every generated format, without rewriting Markdown source files during builds.

- Compared all 19 records in the supplied PubMed dump with the CV; documented duplicates,
  citation differences, missing identifiers, and unmatched works in the publication audit.

- Automatically linked DOI, PMID, and PMCID fields to canonical destinations in generated
  documents, retaining compact identifiers and plain Markdown source.

- Preserved authored field lines in publication and presentation exports, putting titles on their
  own lines; increased spacing between numbered entries from 7 pt to 12 pt in all output formats.

- Added the author-confirmed 2025 year to Lincoln Legacy Teaching and Learning Community;
  checked that all 27 poster/presentation entries include a year.

- Show exact link destinations throughout CV sources, exports, and site navigation; retain social
  platform labels beside visible URLs and correct displayed schemes that differed from targets.

- Numbered publications, presentations, and software entries using ordinary GFM lists. Increased
  heading separation, stepped heading indentation, and justified prose in PDF/DOCX and wide HTML.
- Standardized journal references toward NLM format, added a linked format note, and restored seven
  complete publication bylines from bibliographic sources documented in the citation guide.
- Added a simple GitHub Pages site with the HTML CV and direct PDF/DOCX links. Adapted the
  supplied deployment template into the existing build, with publication restricted to `main`.
- Documented Pages setup and public links; staged only CV documents, CSS, and licensed font assets.
- Updated checkout, setup-python, and upload-artifact to v7 to address the Node.js 20
  deprecation warning reported by the first successful GitHub Actions build.
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
