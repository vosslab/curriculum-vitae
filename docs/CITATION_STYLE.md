# Citation style

Journal references follow the [NLM journal-reference examples](https://www.nlm.nih.gov/bsd/uniform_requirements.html),
which identify ANSI/NISO Z39.29-2005 (R2010), Bibliographic References, as their basis.
This is a biomedical citation convention. The CV includes a short linked note above its references.

Use surname followed by initials, a sentence-case article title in roman type, an abbreviated
journal name, and `year;volume(issue):pages`. Retain available DOI, PMID, and PMCID identifiers.
Use all authors when the full byline is available. Contribution notes follow the reference.
NLM does not require italicizing article titles; this CV uses plain article titles. DOI, PMID, and PMCID values are automatically linked during conversion,
with compact identifier text as an author-approved exception to full-URL display.

Keep references as simple numbered Markdown lists. Writing each marker as `1.` lets GitHub,
Pandoc, and Word generate consecutive numbers when entries are inserted. Software numbering
restarts under each role; publications and presentations each have their own sequence.

## CV line layout

Keep authors, titles, and journal or meeting details on separate source lines within each entry.
The converter preserves these line breaks in publications and presentations. Numbered entries
have 12 pt of space after them. NLM's examples specify citation elements and punctuation; they do
not prescribe line wrapping or inter-entry spacing. We use the author's CV layout while retaining
the citation order and punctuation. See <https://www.nlm.nih.gov/bsd/uniform_requirements.html>.

## Bibliographic verification

The September 30, 2026 formatting pass expanded seven abbreviated journal bylines from:

- CTF Challenge: [PubMed 25913484](https://pubmed.ncbi.nlm.nih.gov/25913484/).
- Engineered mutations: [PubMed 22830650](https://pubmed.ncbi.nlm.nih.gov/22830650/).
- Ab initio toolbox: [PMC2826578](https://pmc.ncbi.nlm.nih.gov/articles/PMC2826578/).
- Appion: [author-hosted published article](https://lander-lab.com/pdfs/19263523.pdf).
- Norovirus structures: [publisher-deposited Crossref record](https://api.crossref.org/works/10.1128/jvi.00314-10).
- Automation: [publisher-deposited Crossref record](https://api.crossref.org/works/10.1016/s0076-6879%2810%2983015-0).
- Alloy optical properties: [Kolodzey's publication list](https://www.eecis.udel.edu/~kolodzey/publications.html),
  entry 58.

The reconciliation pass uses the supplied PubMed dump for its 19 matched citations and the
additional PubMed records for two older biomedical papers. Publisher metadata resolves the
Si(001) byline and alloy volume (313-314). The published list has 23 unique works with complete
available identifiers; the supplied in-preparation manuscript has its own unpublished subsection.

## Items for author review

- The 2019 Fouch manuscript remains marked in preparation; it is not relabeled as published.
- The count is 23 distinct peer-reviewed works, including book chapters; profile citation metrics
  use the supplied September 30, 2026 WoS snapshot.
- Lincoln Legacy Teaching and Learning Community, Open Education Week, and the 2017 Appion
  workshop lack presentation titles. Several other meeting entries retain incomplete author lists.
- Presentation records are numbered but retain their supplied meeting descriptions and roles.
  The NLM journal-reference claim applies to journal articles, not these incomplete meeting records.
- Existing equal-contribution asterisks are preserved; no explanation has been invented.

## PubMed dump comparison

See [PUBLICATION_AUDIT.md](PUBLICATION_AUDIT.md) for the author-supplied search dump comparison,
including citation differences and missing identifiers. The completion note records the changes applied to CV content.

See [ORCID_AUDIT.md](ORCID_AUDIT.md) for comparison with the saved ORCID print view, including
employment dates, department names, publication classification, and identifier coverage.

See [CITATION_METRICS.md](CITATION_METRICS.md) for the dated WoS totals, deduplicated
per-work counts, and remaining gaps in the pasted search results.
