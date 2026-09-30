# Human guidance

<!-- VENDORED HEADER: START -->
Record the durable guidance Neil Voss states, or approves for preservation here, in his own words:
first person or close paraphrase, one to three lines per bullet. Material he supplies as a source
may inform [DESIGN_DECISIONS.md](DESIGN_DECISIONS.md) once it is settled, and an entry of uncertain
origin belongs there too. Rules: [REPO_STYLE.md](REPO_STYLE.md).
[PROPAGATED HEADER - ENTRIES BELOW ARE YOURS]
<!-- VENDORED HEADER: END -->

- Use simple GFM, split into separate Markdown files by CV section so I can go directly to
  publications, software, or another section. Put formatting complexity in the conversion.
- GFM is the source of truth. Word editing will never happen; DOCX is a static, emailable,
  accessible distribution document, alongside PDF.
- My CV is factual information. Preserve its wording and facts; this migration is formatting only.
- Use Atkinson Hyperlegible Next for the CV, Atkinson Hyperlegible Mono for monospace text,
  and IBM Plex Sans Condensed where narrow text is needed. Bundle the needed font weights locally,
  prefer official Braille Institute files, and try slashed-zero with the condensed face.
- Include my supplied YouTube, GitHub, Bluesky, Facebook, and LinkedIn links.
- Keep PDF and DOCX monochrome, with dark blue URLs as the only color.
- Prefer the newer Ubuntu LTS version for the GitHub Actions build runner.
- Publish a simple GitHub Pages CV with PDF and DOCX links, using the starter repository's
  deploy-pages workflow as the template.
- Number publications, posters/presentations, and software entries. Fully justify prose such as
  Research Interests, give headings more space before and less after, and vary heading indentation.
- Use NLM journal citations and cite the format's ANSI/NISO basis for readers from other disciplines.
- Software Development and Support needs a later author-led update: I reported 126 GitHub
  repositories on September 30, 2026. This is guidance for a future edit, not an automatically
  verified CV statistic or authorization to rewrite the existing section.

- Show the actual destination URL for every CV link, including social media and site downloads.
  Destination transparency for cybersecurity takes priority over descriptive-only link labels.
- Every poster/presentation must include a year. Lincoln Legacy Teaching and Learning Community
  was in 2025, as confirmed by the author.
- Separate multiline entries with more paragraph spacing; start publication titles on a new line
  to improve readability while retaining NLM citation content and punctuation.
- DOI, PMID, and PMCID identifiers should be clickable; these are explicit exceptions to the
  full-URL display policy because their standard destinations are recognizable.
- The author confirms that at least two publications absent from the PubMed search dump are
  physics papers outside PubMed; absence from that dump is not grounds to remove them.
- Automatically update the final Last Modified date when building the CV.
- The author supplied PMIDs 10592279 and 11673240 for the two older biomedical papers and
  clarified that these records omit his middle initial.
- The author supplied ORCID https://orcid.org/0000-0003-1392-5187 for the CV.
- Place ORCID in Publications, not at the top of the CV.
- Save the supplied ORCID/ResearcherID metadata for the Si(001) and alloy optical-properties
  papers, including DOIs, contributor lists, WOS identifiers, and record provenance.
- Complete supported reconciliation after comparing sources; do not leave straightforward
  corrections as suggestions requiring another request. Preserve uncertain personal facts rather
  than inventing replacements.
- Keep all printed content, including page-number footers, at least 0.6 inches from the paper
  edge to fit the author's printers; avoid unnecessary 1-inch margins.
- Use the supplied September 30, 2026 free-account Web of Science capture to reconcile citation
  metrics; search results arrive in overlapping batches limited to ten records.
- The author confirms that the WoS high/low citation searches bound each missing paper
  between 32 and 73 citations.
- The author recalls that WoS may contain a duplicated publication; do not equate the profile
  record count or metrics with independently deduplicated CV totals.
- The author supplied the WoS-indexed 2018 NSF cryo-EM community gateway grant,
  which identifies Neil Voss as principal investigator.
- Keep the GitHub README academically focused: prioritize the CV and academic record over
  developer setup, conversion details, and repository maintenance.
- Do not feature ORCID near the top of the README; the author gives it low priority.
- The current department name in 2026 is Department of Biological and Physical Sciences.
- Reduce publication citation wrapping with smaller journal/identifier type, removing the forced
  break before the journal name, or both; retain simple Markdown source.
- Describe Biology Problems in terms of free, open practice questions for students and
  ready-to-use material for educators, using the author's supplied wording.
- Always include `--norestore` when invoking `soffice`, including headless DOCX rendering.
  The installed LibreOffice CLI confirms this spelling; it disables crash recovery.
- Add supported missing CV entries from the service records and our discussion, including
  curriculum development, committee work, LibreTexts contributions, and the student podcast.
- I led the BIOL 201-202 realignment committee, probably Fall 2023 through November 2025.
  November is inferred from the last file edit; use Fall 2025 without claiming an exact end date.
- I think the Roosevelt AI Working Group dissolved in Spring 2026; the end date is recalled,
  rather than independently verified.
- I attended OpenEd 2025 in person for networking and did not formally present.
- I run a podcast with students, with 34 episodes as of September 30, 2026.
- I had unofficial summer research students. Names, year, levels, and projects still need
  confirmation before adding individual supervision entries.
- I chaired the tenure-track Microbiology and Immunology search in Fall 2024/Spring 2025
  and the tenure-track Biochemistry search in Fall 2025/Spring 2026; both were successful hires.
- I have three or four OER books; I supplied the LibreTexts links for Advanced Genetics,
  the ADAPT WeBWorK Handbook, and the BCHM 355/455 Biochemistry book.
- Use year ranges without semesters for faculty search committee dates.
- I was elected Vice Chair of the CSHP College Council in September 2026.
- Date ranges spanning more than one year generally need only years, without months.
- I joined the Northern Illinois LEGO Train Club (NILTC), probably in August 2022, and
  participate in its public library events. I represent myself at these events.
- NILTC plans to change from 501(c)(7) to 501(c)(3) status soon; this is a reported future
  transition, not a confirmed completed change.
- Make the distinction between unbulleted and bulleted material in Research Appointments clear.
- Review Current Position for the same clarity of appointment and affiliation formatting.
- Compare the SERVICE archive with faculty search and other committee entries, focusing on
  membership rather than additional chair roles. I served as CSHP Council secretary off and on
  and wrote its minutes.
- I served on the Senate Executive Committee and the College Executive Committee at the
  same time at some point; I am unsure of the college committee's exact name.
- List Advising Responsibilities newest first. My academic advising is finished because the
  university has moved to centralized advisors.
- I had course buy-outs in Spring 2025 and Spring 2026. I taught BIOL 383/483-10/24,
  Special Topics: Biology and Ethics in Film (remote), again in Summer 2026.
- Departmental peer-review committee service is ongoing, with reviews when someone is up for
  reappointment. Missing documents in a given year do not indicate a gap in service.
- Use the author-supplied faculty handbook revised April 18, 2025 as a terminology reference.
- Do not link to files in `raw/`. Identify source material in prose when needed.
- I have been a required member of the PULSE committee.
- Make the Pages workflow robust: handle imperfect inputs, data, state, and behavior according
  to their context and impact, recovering gracefully to preserve useful operation where possible.
- Bold alone does not sufficiently distinguish Research Appointments titles from their
  collaborator and other detail paragraphs; give the titles clearer heading hierarchy.
- Curriculum Development belongs under Faculty Service, not Teaching Experience.
- I have assisted with all Biochemistry program assessment since the beginning, while
  avoiding a leadership role. My Spring 2011 advanced biochemistry teaching was a launching
  point for the major, which I recall may have formally started in Fall 2011; use an
  approximate 2011 start for assessment service.
- Make Teaching Experience semester headings one heading level smaller (H3 to H4).
- The current 3V website is <https://vosslab.github.io/vossvolvox-pages/>.
- Omit the year from the Biology Problems software heading, consistent with the other
  software headings.
