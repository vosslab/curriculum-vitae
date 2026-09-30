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

**Decision.** Keep publication authors on a separate line, then join the title to journal details
in 10 pt type, including identifier links. Preserve presentation line breaks and use 12 pt after
numbered entries in HTML/PDF and DOCX.

**Why.** The author wants titles and adjacent entries to be easier to distinguish.

**Consequence.** Keep authors, titles, and publication or meeting details on separate source lines.
The converter joins the title and journal lines only for publications, retaining native list
numbering and keeping entries together across pages. Authors, titles, and contribution notes
retain 11 pt type. Other sections retain their existing line wrapping.
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

### Academic README audience

**Decision.** Lead the README with CV downloads, a factual academic overview, and routes to
teaching, research, publications, and service. Keep technical instructions in
[MAINTENANCE.md](MAINTENANCE.md).

**Why.** Academic colleagues are the primary audience for the GitHub landing page.

**Consequence.** Build tools and conversion details remain discoverable through a short link;
academic visitors do not need to install software to read the CV.

**Owner.** [../README.md](../README.md) and [MAINTENANCE.md](MAINTENANCE.md).

### Evidence-backed CV additions

**Decision.** Add documented service, curriculum, OER, software, and presentation entries;
use only supported years and role descriptions. The handbook has its own OER subsection and
does not change the count of 23 peer-reviewed works. Peptidyle is explicitly in development.

**Why.** The author authorized the additions after a read-only survey of the SERVICE archive.
The February 26, 2025 self-evaluation supports program design/approval, the AI Working Group,
College Council secretary, and Senate/College Executive Committee service. The February 14,
2025 task-force agenda names the author; April 18, 2024 council minutes record the secretary
continuation and Research and Professional Leave Committee election.

LibreTexts' [2026 event schedule](https://libretexts.org/blog/opened-week-2026-right-around-corner)
dates the ADAPT talk to March 4 and the AI discussion to March 6. The author-supplied subtitle
file for video LRsjYezafUo identifies Voss as an AI initiative participant at 14:26-14:55 and
as taking the ADAPT effort's lead at 38:03-38:11. These are responsibilities, not an invented
director title. The [handbook](https://chem.libretexts.org/Courses/Remixer_University/The_ADAPT_WeBWorK_Handbook)
credits Neil R. Voss; its AI disclaimer dates its creation to February 2026. Public playlist
metadata identifies *Stump the Vibe Coder* and episode 34; the author supplies the student
involvement and episode count. Peptidyle's current local README describes pre-production status.

**Consequence.** Committee years show documented service, not necessarily complete tenure.
The AI Working Group's Spring 2026 conclusion and realignment committee's Fall 2025 end are
author recollections. Full secretary and executive-committee terms remain unresolved: the
self-evaluation's September 2024 end conflicts with the college committee election record.
The existing March 5, 2025 presentation remains separate from the verified 2026 events.
OpenEd 2025 attendance is not a presentation. Unnamed summer students and Tania Guarneros
Martinez remain pending; the latter's research document does not establish supervision.
Pierre Suessmuth is documented as an OER student worker, but the classification and dates of
supervision need confirmation before adding him to the research roster. No formal program
director appointment or completed realignment outcome is inferred.

**Owner.** [../cv/faculty_service.md](../cv/faculty_service.md),
[../cv/teaching.md](../cv/teaching.md), [../cv/presentations.md](../cv/presentations.md),
[../cv/publications.md](../cv/publications.md), and [../cv/software.md](../cv/software.md).

### Wiki-supported teaching and outreach

**Decision.** Use the supplied Aella wiki's podcast overview and episode summaries to describe
the live student-challenge format and 2026 start. Add the Summer 2026 film course recorded in
its course overview and history. Retain the author's more recent count of 34 podcast episodes.

**Why.** The supplied, untracked wiki pages are titled "Stump the Vibe Coder,"
"BIOL 383/483 - Biology and Ethics in Film," and "BIOL 383/483 Film History and Selection
Inventory." They are local source material rather than published repository documentation.
These summaries identify underlying recordings and course documents; their raw
transcripts and Google Drive sources were not independently reread for this update.

**Consequence.** Treat the wiki as supporting evidence, not a current release inventory.
Individual games and simulations require project-specific review before separate software
entries. The wiki's older episode coverage does not replace the author's count. Student
participation in a stream does not establish an individual research-supervision entry.

**Owner.** [../cv/faculty_service.md](../cv/faculty_service.md) and
[../cv/teaching.md](../cv/teaching.md).

### Year-only extended date ranges

**Decision.** Show years alone for ranges longer than one year, including established ongoing
roles. Apply the same precision to month and semester endpoints.

**Why.** The author prefers less date detail for longer activities.

**Consequence.** Keep months or semesters for shorter appointments, individual events, and
semester teaching headings. Preserve original date evidence in the historical notes.

**Owner.** CV section sources in `cv/`.

### Community outreach through library exhibitions

**Decision.** Group the student podcast and NILTC public-library participation under community
outreach. Use 2022-present for NILTC membership, based on the author's recalled August 2022 start.

**Why.** The author reports personal participation in public library events. The
[NILTC past shows](https://niltc.org/past-shows) list corroborates the club's recurring library
exhibitions, but does not establish which individual shows the author attended.

**Consequence.** Describe public participation without claiming official university
representation, a leadership role, specific event attendance, or formal STEM instruction.
The author reports a planned transition from 501(c)(7) to 501(c)(3); omit tax status from the
CV because it is unnecessary to describe his participation and the transition is not complete.

**Owner.** [../cv/faculty_service.md](../cv/faculty_service.md).

### Research appointment hierarchy

**Decision.** Keep bold appointment lead lines with dates. Use labeled plain paragraphs for
affiliations, advisors, collaborators, and grants; use bullets for activities and contributions.
Apply the same hierarchy to Current Position, with role and institution in the bold lead line.

**Why.** Mixing contextual names and research work in the same lists obscured their roles.

**Consequence.** Some appointments have context only and need no bullet list. Preserve their
existing facts without inventing accomplishments to fill out the layout.

**Owner.** [../cv/research_appointments.md](../cv/research_appointments.md) and
[../cv/current_position.md](../cv/current_position.md).

### Service archive committee reconciliation

**Decision.** Add documented CAS Executive Committee and departmental peer-review membership.
Expand existing committee dates only where records identify the author. Describe CSHP secretary
service as intermittent. Keep the existing faculty search list.

**Why.** Read-only review used `~/Documents/teaching/SERVICE/`; the requested WorkExternal
volume path was unavailable. Evidence includes:

- January 25, 2019 CAS Executive Committee review letters and January 22, 2021 CAS Executive
  Committee letters identify Neil Voss as a member. List those documented years without
  assuming an uninterrupted 2019-2021 term.
- Departmental peer-review letters identify membership in 2016, 2017, 2018, 2020, and 2025.
  The February 2025 self-evaluation also confirms peer-committee service during the 2024 review
  period. Several letters identify him as chair, but this update focuses on membership.
  The author subsequently clarified that this is an ongoing responsibility and that records
  were not saved every year. Use 2016-present, starting with the earliest documented membership,
  and note that reviews are conducted as needed; archival gaps are not service gaps.
  The author-supplied April 18, 2025 faculty handbook, pages 33-34, uses Reappointment,
  Tenure, and Promotion (RTP) and Peer Committee. Use those terms in the CV. The reference is
  the supplied Handbook of the University Faculty, preserved in the raw source archive.
- Council minutes submitted by Neil cover 2021 and 2022. The October 12, 2023 representatives
  roster explicitly records his Fall 2023 co-secretary election alongside Mary Hornick.
  April 2024 election materials and the February 2025 self-evaluation confirm later secretary
  service. The author's clarification establishes intermittent service, not a continuous term.
- The October 2023 roster identifies a College Executive Committee term elected Spring 2022
  and expiring Spring 2024, Senate Executive membership, and Research and Professional Leave
  Committee membership for 2023-2024. April 2024 materials record another one-year leave
  committee election, supporting 2023-2025. The self-evaluation reports executive service
  ending in September 2024.
- The author's recollection of simultaneous Senate and College Executive service agrees with
  the roster evidence: both roles overlap in 2023-2024. The roster calls the college body the
  College Executive Committee within CSHP; the CV spells out the college name for clarity.
- November 2023 council minutes record Neil reporting on the Generative AI Working Group,
  establishing service before the previously listed 2025 start. The Spring 2026 end remains
  author-recalled; the CV now uses years alone.

**Consequence.** Folder possession alone does not establish membership. BA/BS curriculum,
graduate-program committee, and additional CSHP RTP years remain candidates needing clearer
appointment and date evidence. Search folders match already listed searches; this is not proof
that every historical search is represented. Some council files named or filed under 2013
contain 2023 meeting content; use internal dates and corroborating rosters. Preserve private
personnel-review contents in the source archive rather than copying them into CV documentation.

**Owner.** [../cv/faculty_service.md](../cv/faculty_service.md).

### Completed academic advising record

**Decision.** List annual advising counts in reverse chronological order and state that academic
advising concluded after the last listed year, 2025/2026, with centralized advisors.

**Why.** The author confirms that this responsibility has ended and requests newest-first order.

**Consequence.** Preserve all historical counts and notes; do not create a speculative zero-student
2026/2027 entry or imply an end to research supervision.

**Owner.** [../cv/faculty_service.md](../cv/faculty_service.md).

### Distinct teaching preparation count

**Decision.** Report 20 distinct faculty course preparations through Fall 2026. Count lectures
and labs separately, distinct special topics separately, and repeated or cross-listed offerings
once. Treat BCHM 354/454 and 356/456 as the same listed Biochemistry Lab preparation.

**Why.** The listed history contained 17 preparations through Spring 2021. Molecular Biology
(Fall 2021), Biology and Ethics in Film (Spring 2022), and Biostatistics (Fall 2024) raise it to 20.

**Consequence.** Exclude pre-faculty teaching assistantships, course buy-outs, section numbers,
and modality changes. Normalize Application/Applications of Biotechnology as one course.
The count describes the listed history, not independent verification of its completeness or
the teaching-load/contact-hour statement.

**Owner.** [../cv/teaching.md](../cv/teaching.md).
