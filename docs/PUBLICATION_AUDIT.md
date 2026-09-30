# PubMed publication comparison

## Reconciliation completed September 30, 2026

The findings below are the pre-reconciliation audit, retained as evidence. They no longer describe
missing fields in the current CV. The author requested implementation of all supported corrections.

- Merged the two duplicate pairs; the published list now contains 23 distinct works.
- Added all 11 missing DOIs, 17 PMIDs, and 13 PMCIDs from the PubMed dump; retained fuller
  publication dates, Epub dates, and the Stagg erratum notice.
- Aligned the 19 matched bylines and citation details with the supplied PubMed records, including
  CTF author forms and Gerstein M. Preserved contribution notes and equal-contribution markers.
- Restored DoG Picker's missing title word and normalized toolbox and automation title differences.
- Moved the Fouch entry to Unpublished Manuscript, preserving its supplied 2019 in-preparation
  status. A targeted title/author search found the author's earlier CV, not a published record;
  no later publication status is inferred. Source:
  <https://www.roosevelt.edu/sites/default/files/CVs/voss_cv-22sep01.pdf>.
- Changed the opening count to 23 peer-reviewed works, including articles and book chapters.
- Resolved the Si(001) byline against the publisher: Horn von Hogen (with an umlaut on o), Voss N,
  and Tringides M. Source: <https://journals.aps.org/prb/abstract/10.1103/PhysRevB.65.075312>.
- Resolved the alloy volume as 313-314 using publisher-deposited Crossref metadata; included its
  February 1998 date. Source: <https://api.crossref.org/works/10.1016%2Fs0040-6090%2897%2900806-7>.
- Added the Roosevelt department and Scripps research-unit names. Retained the CV's month-level
  employment dates, Scripps Associate title, and Yale degree name rather than overwrite them with
  conflicting ORCID data. Day precision is not needed for this CV. Historical citation metrics
  remain explicitly dated November 2015.

Remaining unknowns are personal facts or absent evidence: the manuscript's later disposition,
the Scripps date/title discrepancy, and missing presentation titles/bylines. These do not prevent
incorporating the supported corrections above, and no values have been invented.

Compared September 30, 2026 against the author-supplied
`raw/summary-vossnrauOR-set.txt` (local, ignored source file) and
[../cv/publications.md](../cv/publications.md). This is a local comparison, not a live PubMed
search or a complete bibliography audit. CV entry numbers refer to the source at review time.
The initial dump comparison did not change publication entries. The subsequent author-supplied
record reconciliation is documented below.

## Coverage and duplicates

- All 19 distinct records in the dump are represented in the CV.
- The CV has 26 entries: 23 distinct published works, two duplicate entries, and one manuscript
  marked in preparation. The count of 23 published works agrees with the introductory count
  after excluding duplicates and the in-preparation manuscript; publication status was not
  independently verified for entries absent from the dump.
- CV entries 2 and 4 duplicate the RNA nanostructures paper, PMID 29039189.
- CV entries 3 and 5 duplicate the cucumber necrosis virus paper, PMID 28724762.
- Four published entries are absent from this dump: Si(001) step dynamics (2002), minimum atom
  types (2001), non-canonical RNA base-pair database (2000), and alloy optical properties (1998).
  The author confirms the two physics/materials papers (Si(001) in Physical Review B and alloys
  in Thin Solid Films) are outside PubMed; their absence is expected. The other two are in
  Bioinformatics and Nucleic Acids Research. Their absence from this particular search result
  does not establish whether PubMed indexes them or indicate an error in the CV.
- The Fouch 2019 manuscript remains in preparation under Peer-Reviewed Publications; its current
  status needs author confirmation. The dump cannot establish whether it was later published.

## Citation differences

| CV entry | Field | Current CV | Supplied PubMed dump |
| --- | --- | --- | --- |
| 7, CTF Challenge | Author name | Heymann JB | Bernard Heymann J |
| 7, CTF Challenge | Author initials | Sorzano COS | Sorzano CO |
| 21, ribosomal exit tunnel | Author initials | Gerstein MB | Gerstein M |
| 22, RNA atomic volumes | Author initials | Gerstein MB | Gerstein M |
| 18, DoG Picker | Title wording | tools to facilitate | software tools to facilitate |
| 15, toolbox | Title typography | 3D | 3-D |
| 17, automation | Title punctuation | microscopy: connecting | microscopy connecting |
| 3 and 5, cucumber necrosis virus | Article locator | 91(19). pii: e01030-17 | 91(19):e01030-17 |

The CTF author-name differences conflict with the earlier verification pass; the supplied dump
records the differences above, but this comparison does not determine the preferred personal-name
form. DoG Picker's equal-contribution asterisks are CV annotations absent from the dump, not an
author-order discrepancy. Other matched author lists agree.

The dump includes an erratum notice missing from CV entry 20 (Stagg):
`Erratum in: J Struct Biol. 2010 Aug;171(2):244.` This refers to a correction, not a retraction.

Other differences are title capitalization, optional publication months/days and Epub dates,
and expanded versus shortened page ranges (477-492 versus 477-92). No conflicting publication
year, volume, issue, or page range was found among matched records. These differences should not
all be treated as errors: the CV intentionally uses sentence-case titles and abbreviated pages.
The original November 2015 citation count and h-index cannot be checked from this dump.

## Missing identifiers

Across the 19 matched distinct papers, the CV lacks 11 DOIs, 17 PMIDs, and 13 PMCIDs supplied
in the dump. Existing identifiers agree with the dump. All 19 dump records have DOIs and PMIDs;
14 have PMCIDs. Counts below use one CV entry per distinct paper, excluding its duplicate.

| Dump record | CV entry | PMID in dump | Identifiers missing from CV |
| --- | --- | --- | --- |
| 1 | 7 | 25913484 | PMID, PMCID |
| 2 | 2 | 29039189 | PMCID |
| 3 | 9 | 22308316 | PMID, PMCID |
| 4 | 6 | 26080023 | PMID |
| 5 | 13 | 20455239 | doi, PMID, PMCID |
| 6 | 8 | 22830650 | PMID, PMCID |
| 7 | 14 | 20335264 | doi, PMID, PMCID |
| 8 | 21 | 16784753 | doi, PMID |
| 9 | 3 | 28724762 | None |
| 10 | 17 | 20888480 | PMID |
| 11 | 19 | 19263523 | doi, PMID, PMCID |
| 12 | 12 | 20478824 | doi, PMID, PMCID |
| 13 | 15 | 20018246 | doi, PMID, PMCID |
| 14 | 18 | 19374019 | doi, PMID, PMCID |
| 15 | 22 | 15670598 | doi, PMID |
| 16 | 20 | 18534866 | doi, PMID, PMCID |
| 17 | 10 | 20729899 | doi, PMID, PMCID |
| 18 | 16 | 20888970 | doi, PMID |
| 19 | 11 | 20802494 | PMID, PMCID |

## Suggested reconciliation

Merge each duplicate pair while retaining the fuller date and all identifiers. Add the identifiers
from the dump, restore "software" in the DoG Picker title, reconcile author-name discrepancies,
and add the Stagg erratum notice. Keep contribution notes. Check the two unmatched biomedical papers separately if desired; the two physics/materials
papers are expected to be absent. Confirm the Fouch manuscript's status before changing its classification.

## Author-supplied additional record

The author subsequently supplied <https://pubmed.ncbi.nlm.nih.gov/10592279/> for the 2000
non-canonical RNA base-pair database paper. Metadata was retrieved from the Europe PMC core
record for PMID 10592279 because the PubMed page returned no readable record in this session:
<https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=EXT_ID:10592279%20AND%20SRC:MED&format=json&resultType=core>.

The CV now uses the indexed author form Voss N, the January 1, 2000 publication date,
DOI 10.1093/nar/28.1.375, PMID 10592279, and PMCID PMC102435. This confirms that the paper
is indexed despite being absent from the supplied dump. The second author-supplied record below resolves the remaining biomedical paper. The dump comparison counts
remain historical and apply only to its original 19 records.

The author also supplied <https://pubmed.ncbi.nlm.nih.gov/11673240/> for the 2001 minimum
protein-atom types paper. Europe PMC confirms Tsai J, Voss N, Gerstein M; Bioinformatics.
2001 Oct;17(10):949-956; DOI 10.1093/bioinformatics/17.10.949; PMID 11673240. No PMCID is
provided by that record. Metadata source:
<https://www.ebi.ac.uk/europepmc/webservices/rest/search?query=EXT_ID:11673240%20AND%20SRC:MED&format=json&resultType=core>.

The CV now matches these initials and includes its DOI and PMID. Both additional biomedical
papers are indexed as Voss N. Together with the 19-record dump, these establish matches for
21 distinct published works; the remaining two published works are the physics/materials papers.

## Author-supplied physics records

On September 30, 2026, the author supplied the following ORCID/ResearcherID records.
The full pasted text is saved locally as `raw/orcid_physics_records.txt` (ignored by Git).
This section preserves the bibliographic evidence in repository documentation. These are
supplied records, not independently fetched publisher metadata.

### Si(001) step dynamics

- Title: Si(001) step dynamics: A temporal low-energy electron diffraction study
- Journal: Physical Review B; year: 2002; type: Journal article
- DOI: 10.1103/PhysRevB.65.075312
- WOSUID: WOS:000174030900066
- Contributors: Kammler, M.; von Hogen, M. H.; Voss, N.; Tringides, M.; Menzel, A.; Conrad, E. H.
- Added: 2017-05-02; last modified: 2022-05-25
- Source: Neil Voss via ResearcherID
- Record URL:
  <http://gateway.webofknowledge.com/gateway/Gateway.cgi?GWVersion=2&SrcAuth=ORCID&SrcApp=OrcidOrg&DestLinkType=FullRecord&DestApp=WOS_CPL&KeyUT=WOS:000174030900066&KeyUID=WOS:000174030900066>

The DOI has been added to the existing CV entry. The supplied initials Voss N and Tringides M
are shorter than the CV's Voss NR and Tringides MC; existing bylines are retained pending
reconciliation with the published article. The pasted record does not supply volume or pages.

### Alloy optical properties

- Title: Optical properties and band structure of Ge1-yCy and Ge-rich Si1-x-yGexCy alloys
- Journal: Thin Solid Films; year: 1998; type: Journal article
- DOI: 10.1016/s0040-6090(97)00806-7
- WOSUID: WOS:000073761700030
- Contributors: Junge, K. E.; Voss, N. R.; Lange, R.; Dolan, J. M.; Zollner, S.; Dashiell, M.;
  Hits, D. A.; Orner, B. A.; Jonczyk, R.; Kolodzey, J.
- Added: 2017-05-02; last modified: 2022-05-25
- Record URL:
  <http://gateway.webofknowledge.com/gateway/Gateway.cgi?GWVersion=2&SrcAuth=ORCID&SrcApp=OrcidOrg&DestLinkType=FullRecord&DestApp=WOS_CPL&KeyUT=WOS:000073761700030&KeyUID=WOS:000073761700030>

The DOI has been added to the existing CV entry. Author order and initials agree. The pasted
record supplies no volume or pages, so it does not resolve the earlier 313 versus 313-314 issue.
Its Added and Last modified dates describe the ORCID record, not the article publication date.

All 23 distinct published works now have supplied supporting records: the 19-record PubMed dump,
two additional PubMed records, and these two physics/materials records. The original dump audit's
remaining reconciliation tasks still apply.
