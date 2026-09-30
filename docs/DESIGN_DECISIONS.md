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
author's direction. The original "Last Modified" line is historical source text, not a build date.

**Owner.** The Markdown files under `cv/`.
