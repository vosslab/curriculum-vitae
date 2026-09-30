# ORCID print-view comparison

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

Compared September 30, 2026 using the local file
`raw/Neil_Voss_0000-0003-1392-5187-ORCID_Print_view.html` (Git-ignored) and the 14 CV sections.
This report describes that saved snapshot; it does not establish the current live ORCID contents.
CV source content was not changed by this review. Publication entry numbers are review-time numbers.

## Coverage

- All 22 works in the ORCID snapshot already appear in the CV. There are no newly discovered works.
- All three employments and the Yale PhD already appear in the CV.
- ORCID iD, structural biology and electron microscopy interests, and US location are represented.
  The standalone keyword and country fields would be optional repetition in a CV.
- The CV is more complete: its 2017 RNA nanostructures paper is absent from this ORCID snapshot.
  It also includes Iowa State degrees, additional appointments, teaching, grants, service,
  software, supervision, honors, and presentations not represented as activities in the snapshot.
- The CV still has the two publication duplicate pairs and the in-preparation manuscript noted in
  [PUBLICATION_AUDIT.md](PUBLICATION_AUDIT.md). The snapshot does not settle the manuscript's status.

## Additional employment and education detail

| Record | Detail in ORCID | Current CV / implication |
| --- | --- | --- |
| Roosevelt associate professor | Start 2016-08-15 | Aug. 2016; day precision is additional, not a conflict |
| Roosevelt assistant professor | 2010-08-15 through 2016-08-15 | Aug. 2010 through Aug. 2016; day precision is additional |
| Both Roosevelt roles | Department: Biological, Chemical, and Physical Sciences | Department name is absent from the CV |
| Scripps postdoctoral role | Department: National Resource for Automated Molecular Microscopy | Full organizational unit is absent from the appointment entry |
| Scripps postdoctoral role | 2007-01-01 through 2010-07-31 | CV says Dec. 2006 through Aug. 2010; dates differ |
| Scripps postdoctoral role | Post-doctoral Fellow | CV says Post-doctoral Associate; role wording differs |
| Yale education | 2000-09-01 through 2007-05-01 | CV education gives 2000-2007 and PhD 2007; months/days are additional |
| Yale department | Molecular Biochemistry and Biophysics | CV says Molecular Biophysics and Biochemistry; word order differs |

The CV separately lists Yale graduate research through November 2006. That is a different record
from the 2007 degree award and should not automatically be treated as a contradiction. ORCID's
first-of-month dates are supplied values; their administrative precision has not been verified.
The saved print view does not provide contributor lists, so it cannot reconcile author initials.

## Missing DOI fields

These 11 DOIs are in ORCID but absent from the corresponding CV entries. They are the same
11 missing DOIs identified in the supplied PubMed dump, providing corroboration rather than
new missing papers. Other DOI values agree when compared without case distinctions.

| CV entry | Work | DOI supplied by ORCID |
| --- | --- | --- |
| 12 | 3V: cavity, channel and cleft volume calculator and extractor | 10.1093/nar/gkq395 |
| 15 | A Toolbox for ab initio 3-D reconstructions in single-particle electron microscopy | 10.1016/j.jsb.2009.12.005 |
| 10 | A polyhedron made of tRNAs | 10.1038/nchem.733 |
| 14 | High-Resolution Cryo-Electron Microscopy Structures of Murine Norovirus 1 and Rabbit Hemorrhagic Disease Virus Reveal Marked Flexibility in the Receptor Binding Domains | 10.1128/jvi.00314-10 |
| 13 | Multivalent Display and Receptor-Mediated Endocytosis of Transferrin on Virus-Like Particles | 10.1002/cbic.201000125 |
| 16 | SOFTWARE TOOLS FOR MOLECULAR MICROSCOPY: AN OPEN-TEXT WIKIBOOK | 10.1016/s0076-6879(10)82016-6 |
| 19 | Appion: An integrated, database-driven pipeline to facilitate EM image processing | 10.1016/j.jsb.2009.01.002 |
| 18 | DoG Picker and TiltPicker: Software tools to facilitate particle selection in single particle electron microscopy | 10.1016/j.jsb.2009.01.004 |
| 20 | A test-bed for optimizing high-resolution single particle reconstructions | 10.1016/j.jsb.2008.04.005 |
| 21 | The geometry of the ribosomal polypeptide exit tunnel | 10.1016/j.jmb.2006.05.023 |
| 22 | Calculation of standard atomic volumes for RNA and comparison with proteins: RNA is packed more tightly | 10.1016/j.jmb.2004.11.072 |

The snapshot also contains 21 Web of Science identifiers and their gateway URLs. These are absent
from CV citations but are optional database metadata, not missing publications. The snapshot has
only one PMID (28724762), already in the CV, and supplies no PMCIDs. The PubMed dump provides
richer PMID/PMCID coverage.

## Publication differences to retain for review

- ORCID classifies the two Methods in Enzymology contributions (Automation and Wikibook) as
  book chapters. The CV groups them with peer-reviewed publications and describes all 23 works
  as journal articles in its opening sentence. This classification deserves author review;
  the print view alone is not a reason to move or remove the entries.
- The cucumber necrosis virus paper has date 2017-07 in ORCID, while the fuller CV record and
  PubMed dump give September 12, 2017. This may reflect online versus issue publication dates;
  that explanation is an inference, not verified by this snapshot.
- ORCID's cucumber paper title says "Quasi Six-fold" versus "quasi-6-fold" in the CV/PubMed dump.
- DoG Picker's title includes "Software tools"; the CV omits "software".
- The toolbox title uses "3-D" rather than the CV's "3D".
- The snapshot gives no volume, issue, or page fields, so it cannot resolve the alloy volume
  discrepancy (313 versus 313-314). Journal names are generally expanded rather than abbreviated.

## Suggested next changes

Add the corroborated DOI fields and, if desired, the department/unit names. Confirm Scripps dates
and role wording before altering those facts. Keep the current degree name pending confirmation.
Handle duplicate publications and the in-preparation manuscript using the separate publication audit.
No new CV work needs to be added from this ORCID snapshot.
