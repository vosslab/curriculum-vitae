# Design decisions

<!-- VENDORED HEADER: START -->
Record each durable decision about how this code and repository are shaped, once it is settled, with
the reasoning a later reader needs. Guidance Neil Voss states belongs in
[HUMAN_GUIDANCE.md](HUMAN_GUIDANCE.md), dated history in `docs/CHANGELOG.md`, open discussion in
`docs/active_plans/decisions/`. [PROPAGATED HEADER - ENTRIES BELOW ARE YOURS]
<!-- VENDORED HEADER: END -->

Write each decision as a level-three heading with these four fields. `Owner` names the
authoritative code or contract document, rather than a person.

```markdown
### <decision title>

**Decision.** <the durable direction>

**Why.** <the reason it was chosen>

**Consequence.** <the constraint a future change preserves>

**Owner.** <the authoritative code or contract doc>
```

### Section files are authoritative

**Decision.** Each file under `cv/` contains one CV section in simple GFM.
[../cv/sections.txt](../cv/sections.txt) defines their assembly order. Combined Markdown, HTML,
PDF, and DOCX are generated into ignored `output/`.

**Why.** Individual sections are easier to update, and GitHub renders the sources directly.

**Consequence.** The build checks that every section is listed exactly once. It never edits the
sources or reads the original Google Docs exports. Formatting migration preserves content;
the author's supplied social links are the only content addition.

**Owner.** [../build_cv.py](../build_cv.py) and [../cv/sections.txt](../cv/sections.txt).

### Presentation belongs to conversion

**Decision.** Pandoc reads GFM. WeasyPrint renders styled HTML to tagged PDF; Pandoc and a small
DOCX postprocessor apply document styles, native continuous column sections, and embedded fonts.
There is no editable Word template or Word-to-Markdown workflow.

**Why.** The sources need only headings, paragraphs, lists, and links. Selected yearly lists under
Research Supervision receive two-column presentation without source-level layout markup.

**Consequence.** GitHub keeps ordinary lists. HTML becomes single-column on narrow screens.
PDF and DOCX have independent pagination. The same HTML also supplies the public GitHub Pages CV.

**Owner.** [../build_cv.py](../build_cv.py) and [../styles/cv.css](../styles/cv.css).

### Publish the existing build

**Decision.** Stage a static site in ignored `output/site/` with format links, the HTML CV,
PDF, DOCX, stylesheet, and verified font assets. Deploy it after successful main-branch builds.

**Why.** Visitors need stable public document links without an Actions artifact download.
Reusing the document build keeps the site and downloadable CV consistent.

**Consequence.** Pull requests never deploy. Only the deploy job receives Pages write and
OIDC permissions. Pages uses GitHub Actions as its source; generated files stay out of Git.

**Owner.** [../.github/workflows/build.yml](../.github/workflows/build.yml) and
[../build_cv.py](../build_cv.py).

### Fonts travel with the outputs

**Decision.** Bundle pinned static TrueType files from the Atkinson upstream projects and IBM Plex,
with checksums, full license notices, PDF subsets, and standard DOCX font embedding.

**Why.** Static files are suitable for document embedding. Upstream OFL releases provide direct,
reproducible distribution files; the Braille Institute website currently uses a download form.

**Consequence.** Builds verify font assets and use local resources. Slashed-zero applies to
condensed text in HTML/PDF; DOCX does not claim equivalent OpenType-feature support in every reader.

**Owner.** [../assets/fonts/README.md](../assets/fonts/README.md).

### Preserve source uncertainties

**Decision.** Preserve apparent duplicate publications, dated metrics, the original modification
date, and wording such as "ree and open problem sets" exactly as supplied, apart from whitespace
and typographic punctuation normalization.

**Why.** The author explicitly limited this migration to formatting and factual preservation.

**Consequence.** Future factual corrections happen in the appropriate source section at the
author's direction. The original fixed "Last Modified" line has been superseded by the author-requested automatic
build date described below.

**Owner.** The Markdown files under `cv/`.

### Citation and hierarchy presentation

**Decision.** Use native ordered lists for publications, presentations, and software; apply NLM
journal-reference conventions with a linked note. Justify prose in document outputs and wide HTML,
use left alignment on narrow screens and in lists, and progressively indent subsection headings.

**Why.** The author requested clearer grouping, less crowded headings, and an explicit biomedical
citation convention. Complete verified bylines replace the original mid-list omissions.

**Consequence.** Markdown remains simple. Numbering is generated, software lists restart by role,
and document pagination may grow. Bibliographic verification and unresolved gaps are recorded in
[CITATION_STYLE.md](CITATION_STYLE.md); the earlier formatting-only rule now permits these requested
citation changes, while factual uncertainties remain visible for author review.

**Owner.** [../styles/cv.css](../styles/cv.css), [../build_cv.py](../build_cv.py), and
[CITATION_STYLE.md](CITATION_STYLE.md).

### Visible link destinations

**Decision.** Use simple GFM autolinks in CV sources and exact destination text for all exported
hyperlinks. Keep contextual names beside URLs. Show full public URLs in the site's download links.

**Why.** The author prioritizes inspecting destinations before clicking. This overrides the shared
Markdown guide's preference for descriptive-only external link text in the CV.

**Consequence.** The converter enforces matching link text and target in HTML, PDF, and DOCX.
Long URLs retain the condensed font. Existing destinations are preserved, including HTTP schemes;
visible URLs do not certify the safety of a destination or its redirects.

**Owner.** [../build_cv.py](../build_cv.py) and the Markdown sources under `cv/`.

### Multiline citation layout

**Decision.** Preserve authored source line breaks inside numbered publication and presentation
entries during conversion; use 12 pt after numbered entries in HTML/PDF and DOCX.

**Why.** The author wants titles and adjacent entries to be easier to distinguish.

**Consequence.** Keep authors, titles, and publication or meeting details on separate source lines.
The converter turns those newlines into visible line breaks, retaining native list numbering and
keeping entries together across pages. Other sections retain ordinary Markdown line wrapping.
NLM citation content and punctuation remain unchanged; this is a CV layout choice.

**Owner.** [../build_cv.py](../build_cv.py) and [../styles/cv.css](../styles/cv.css).

### Clickable citation identifiers

**Decision.** Convert plain `doi:`, `PMID:`, and `PMCID:` fields into links to doi.org,
pubmed.ncbi.nlm.nih.gov, and pmc.ncbi.nlm.nih.gov respectively, showing the identifier only.

**Why.** The author explicitly exempts these recognizable identifiers from full-URL display.

**Consequence.** GFM stays plain; generated HTML, PDF, and DOCX gain links. Sentence punctuation
stays outside the link and DOI parentheses remain part of the identifier. Other links still show
full destinations. Missing or unrecognized identifiers remain untouched.

**Owner.** [../build_cv.py](../build_cv.py).

### Automatic modification date

**Decision.** Append the build date as the final Last Modified paragraph during source assembly
for distribution. Use America/Chicago consistently in local and GitHub Actions builds.

**Why.** The author requested automatic replacement of the stale August 25, 2023 date.

**Consequence.** Every generated format shares one date, including assembled Markdown and the
Pages site. Source section files need no manual date edits. This is the build date, not a Git
commit timestamp; rebuilding on a later day advances it even if CV content has not changed.

**Owner.** [../build_cv.py](../build_cv.py).

### Reconciled bibliography and source conflicts

**Decision.** Incorporate verified bibliographic metadata, merge duplicate works, separate the
unpublished manuscript, and retain 23 published works. Use PubMed for matched citations and
publisher metadata for physics-paper discrepancies. Preserve author contribution annotations.

**Why.** The author requested completion of the audited reconciliation, without another approval step.

**Consequence.** The source is more complete while historical metrics remain dated. Conflicting
personal appointment dates retain the author's CV version; the saved ORCID alternative remains
in the audit. The 2019 in-preparation statement is preserved without claiming later publication.

**Owner.** [../cv/publications.md](../cv/publications.md), [PUBLICATION_AUDIT.md](PUBLICATION_AUDIT.md),
and [ORCID_AUDIT.md](ORCID_AUDIT.md).

### Printer-safe footer placement

**Decision.** Keep 0.6-inch top and side margins and place footers at least 0.6 inches above the
bottom edge. Reserve a 0.25-inch footer band by ending body content 0.85 inches above the bottom.

**Why.** The author's printers require 0.6-inch clearance, including footers. The body and footer
need separate space to avoid overlap.

**Consequence.** PDF and DOCX use the same printable bounds; pagination may grow slightly.

**Owner.** [../build_cv.py](../build_cv.py) and [../styles/cv.css](../styles/cv.css).

### Dated Web of Science metrics

**Decision.** Use the supplied profile dashboard's 2,961 citations and h-index 17, dated September
30, 2026. Preserve deduplicated per-paper counts and source gaps in
[CITATION_METRICS.md](CITATION_METRICS.md), without adding counts to every citation.

**Why.** The dashboard provides aggregate values even though the pasted search batches omit two
main works. Repeated search results and reference counts must not inflate citation counts.

**Consequence.** Unknown per-paper counts remain unknown. The CV has 23 main works; the dashboard
has 24 records, with the composition unresolved because the author recalls a possible database
duplicate in addition to the separately listed correction. The older 2015 metric snapshot
is retained in the metrics report as history rather than displayed as current.

**Owner.** [../cv/publications.md](../cv/publications.md) and [CITATION_METRICS.md](CITATION_METRICS.md).
