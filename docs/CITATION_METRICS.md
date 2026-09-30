# Web of Science citation snapshot

Source: author-supplied `raw/wos-citation-counts-2026-sept-30.txt` (local, Git-ignored),
captured September 30, 2026. These are supplied Web of Science Core Collection figures,
not independently retrieved live counts. This tracked report preserves the extracted counts.

## Profile metrics

| Metric | Reported value |
| --- | --- |
| Publications / total documents | 24 |
| Sum of Times Cited | 2,961 |
| H-index | 17 |
| Citing Articles | 2,461 |
| Sum of Times Cited without self-citations | 2,934 |
| Citing Articles without self-citations | 2,444 |
| Sum of Times Cited by Patents | 76 |
| Citing Patents | 63 |
| Sum of Times Cited by Policy | 0 |
| Citing Policy Documents | 0 |

The profile also reports 24 indexed Core Collection publications, zero preprints, dissertations,
non-indexed publications, verified peer reviews, and verified editor records; it lists one awarded
grant. These profile inventory fields are not complete career counts and are not copied into the CV.

The author subsequently supplied the indexed grant title and PI field from
<https://www.webofscience.com/wos/author/record/K-6244-2012>. It matches the existing
CV grant "Collaborative Research: ABI Development: Building a Community Gateway for
Cryo-Electron Microscopy Structure Determination," NSF award 1759735. The official
NSF API, retrieved September 30, 2026, confirms Neil R Voss as PI, Roosevelt University,
and $26,244 obligated: <https://api.nsf.gov/services/v1/awards/1759735.json>.
The response is saved in `raw/nsf_award_1759735.json` (local, Git-ignored). The CV now
identifies Neil Voss as PI; this is additional detail for an existing grant, not a new award.

The CV's introductory metrics now use the reported 2,961 citations and h-index 17 with the capture
date. They replace the November 9, 2015 snapshot of 1,696 citations and h-index 15. The public
wording identifies these as profile metrics, rather than a total independently computed from
incomplete per-paper counts. Individual counts are retained here instead of cluttering citations.

## Extraction and completeness

- Four pasted batches contain 40 result appearances: 38 appearances of main works and two of
  the Stagg correction. Deduplication gives 21 main works with citation counts and one correction.
- Seventeen repeated main-work appearances have identical counts; each work is counted once.
- The 21 captured main-work counts sum to 2,855. Their observed-subset h-index is 15. The author confirms the high/low citation-sort searches
  bound each missing main work at 32-73 citations. Including either bound yields h-index 17,
  matching the dashboard under the assumption that captured counts represent one record per
  distinct work. A true database duplicate requires checking record-level counts before calling
  this a deduplicated h-index.
- The gap from the profile total is 106 citations. It cannot be allocated between missing records
  from this export alone, especially while the author-recalled WoS duplicate is unresolved.
- No explicit citation count appears for the correction. Its `0 Reference` is a reference count,
  not evidence of zero citations. Other `0 References` fields are not used as citation counts.
- The two missing main works plus 21 captured main works and the separately listed correction
  could explain the profile's 24 publications. However, the author recalls a duplicated WoS
  publication. The pasted results omit WoS record IDs, so repeated title appearances cannot
  distinguish overlapping searches from separate database records. The 24-record composition
  is unresolved; the correction-only explanation is not established. The CV keeps 23 distinct main works and its existing
  correction notice, without counting the correction as another research publication.

## Per-publication counts

CV numbering is as of this review. DOI is the stable match key for future updates. An exact missing
count remains unknown; the author-confirmed search bounds are recorded instead of zero. These counts include self-citations unless the supplied source says
otherwise; only the dashboard provides the separate total excluding self-citations.

| CV entry | Work | Citations | DOI |
| --- | --- | --- | --- |
| 1 | Composing RNA nanostructures from a syntax of RNA structural modules. | 64 | 10.1021/acs.nanolett.7b03842 |
| 2 | Stability of cucumber necrosis virus at the quasi-6-fold axis affects zoospore transmission. | 4 | 10.1128/JVI.01030-17 |
| 3 | Visualization and quality assessment of the contrast transfer function estimation. | 11 | 10.1016/j.jsb.2015.06.012 |
| 4 | CTF challenge: result summary. | 27 | 10.1016/j.jsb.2015.04.003 |
| 5 | Engineered mutations change the structure and stability of a virus-like particle. | 73 | 10.1021/bm300590x |
| 6 | Subunit architecture of general transcription factor TFIIH. | 45 | 10.1073/pnas.1105266109 |
| 7 | A polyhedron made of tRNAs. | 145 | 10.1038/nchem.733 |
| 8 | In vitro assembly of cubic RNA-based scaffolds designed in silico. | 278 | 10.1038/nnano.2010.160 |
| 9 | 3V: cavity, channel and cleft volume calculator and extractor. | 406 | 10.1093/nar/gkq395 |
| 10 | Multivalent display and receptor-mediated endocytosis of transferrin on virus-like particles. | 108 | 10.1002/cbic.201000125 |
| 11 | High-resolution cryo-electron microscopy structures of murine norovirus 1 and rabbit hemorrhagic disease virus reveal marked flexibility in the receptor binding domains. | 32-73 (bounded) | 10.1128/JVI.00314-10 |
| 12 | A toolbox for ab initio 3-D reconstructions in single-particle electron microscopy. | 32-73 (bounded) | 10.1016/j.jsb.2009.12.005 |
| 13 | Software tools for molecular microscopy: an open-text Wikibook. | 7 | 10.1016/S0076-6879(10)82016-6 |
| 14 | Automation in single-particle electron microscopy connecting the pieces. | 20 | 10.1016/S0076-6879(10)83015-0 |
| 15 | DoG Picker and TiltPicker: software tools to facilitate particle selection in single particle electron microscopy. | 459 | 10.1016/j.jsb.2009.01.004 |
| 16 | Appion: an integrated, database-driven pipeline to facilitate EM image processing. | 689 | 10.1016/j.jsb.2009.01.002 |
| 17 | A test-bed for optimizing high-resolution single particle reconstructions. | 32 | 10.1016/j.jsb.2008.04.005 |
| 18 | The geometry of the ribosomal polypeptide exit tunnel. | 255 | 10.1016/j.jmb.2006.05.023 |
| 19 | Calculation of standard atomic volumes for RNA and comparison with proteins: RNA is packed more tightly. | 118 | 10.1016/j.jmb.2004.11.072 |
| 20 | Si(001) step dynamics: A temporal low-energy electron diffraction study. | 7 | 10.1103/PhysRevB.65.075312 |
| 21 | Determining the minimum number of types necessary to represent the sizes of protein atoms. | 14 | 10.1093/bioinformatics/17.10.949 |
| 22 | Database of non-canonical base pairs found in known RNA structures. | 92 | 10.1093/nar/28.1.375 |
| 23 | Optical properties and band structure of Ge(1-y)C(y) and Ge-rich Si(1-x-y)Ge(x)C(y) alloys. | 1 | 10.1016/s0040-6090(97)00806-7 |

## Remaining source gaps

Only these per-paper counts are missing:

- Norovirus structures, DOI 10.1128/JVI.00314-10: 32-73 citations.
- Ab initio toolbox, DOI 10.1016/j.jsb.2009.12.005: 32-73 citations.

The bounds follow the author's confirmation that the two relevant batches are the highest- and
lowest-cited results, with cutoffs of 73 and 32. Exact values are not inferred.

The correction's citation count is also unreported. No estimate or subtraction-derived allocation
has been inserted. The supplied profile totals are sufficient to update the CV summary now.

## Possible duplicate in WoS

The author recalls a duplicated publication in WoS. Its identity and record IDs are not supplied.
The CV correctly retains 23 distinct published works. The 2,961 citations and h-index 17 remain
explicitly labeled as reported profile metrics, not independently deduplicated metrics. Do not
subtract a presumed duplicate, merge citation counts, or allocate the 106-citation difference
until the underlying records can be identified. Repeated appearances of a title in overlapping
search batches are not by themselves proof of a database duplicate.
