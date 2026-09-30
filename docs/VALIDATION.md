# CV validation

## Numbering and layout revision

The later September 30 revision produces a 15-page PDF and an 18-page LibreOffice rendering of
the DOCX. All pages were inspected in rendered contact sheets; printable-boundary checks found
no clipped text. The browser passes at 390, 768, and 1280 pixels without horizontal overflow.
Prose is justified in PDF/DOCX and wide HTML; narrow HTML and lists remain left aligned.

The sources render as 26 publication entries, 27 presentation entries, and software lists of
8, 2, and 2 entries under their respective roles. Software and presentation words are unchanged;
all original publication DOIs remain, including duplicates. Journal citation formatting and seven
verified byline expansions supersede the original migration's exact-text preservation for those
entries; sources and unresolved metadata gaps are in [CITATION_STYLE.md](CITATION_STYLE.md).
All 119 repository checks pass, along with Python static checks and `git diff --check`.
These results are local; revised artifacts still require a push for the Pages workflow to publish.

## Content preservation

The original DOCX, Markdown, and PDF exports in ignored `raw/` were used for migration. A normalized
word-frequency comparison against the original DOCX found no missing original words, including
repeated entries. The added words are the author-supplied social section and platform names.
Formatting normalization replaces nonbreaking spaces and typographic quotation marks/dashes with
plain source characters. Original factual wording, including apparent typos and dated statements,
remains in the section files.

The finished DOCX text also matches the assembled source exactly after whitespace normalization.
PDF text matches after removing generated list labels and page footers. All original hyperlink
targets remain; GFM additionally makes the existing plain Biology Problems URL clickable.

## Build checks

```bash
source source_me.sh && python3 build_cv.py
source source_me.sh && python3 -m pytest tests/ --no-ascii-fix
```

The focused conversion tests verify text preservation, selection of yearly supervision groups,
native DOCX lists and columns, intact embedded font bytes, local-only rendering resources, and
complete section assembly. Repository checks cover Markdown links, characters, and whitespace.
Automatic source-text fixing is disabled for validation.

## September 30 verification

| Check | Result |
| --- | --- |
| Repository and conversion tests | 110 passed |
| Python static check | `pyflakes` passed for the build and conversion tests |
| PDF | 13 US Letter pages; tagged; English language metadata; embedded fonts |
| DOCX | Opens and renders through LibreOffice; source text preserved; seven embedded font faces |
| Independent build | Clean source copy builds without `raw/` or pre-existing output |
| Font isolation | PDF builds with Fontconfig restricted to the bundled font directory |
| Browser widths | 390, 768, and 1280 pixels; no horizontal overflow |
| Browser preferences | Light and dark preferences retain the deliberate white document surface |
| Student lists | One column at 390 pixels, two at wider widths; native DOCX column sections |
| Links | Keyboard reachable; long URLs use the condensed font and CSS slashed-zero |

The local tools were Pandoc 3.11, WeasyPrint 70.0, python-docx 1.2.0, and LibreOffice 26.2.6.3.
The font notices are preserved byte-for-byte from upstream and excluded only from whitespace
rewriting; their original checksums remain enforced by the build.

## Visual and accessibility review

The Pages addition was checked locally at 390 and 1280 pixels, including the format navigation.
All local HTML links and CSS font references resolve within the staged site. Downloaded document
bytes match the PDF and DOCX build outputs; no original exports, QA files, or Git files are staged.
All 118 repository checks pass. Live Pages deployment has not yet been verified: the available
GitHub API credential returned HTTP 401, and the workflow changes still need committing and pushing.

Local verification includes PDF page rendering, a LibreOffice rendering of the DOCX, and browser
checks of the HTML preview at narrow and wide widths. Rendering evidence belongs in ignored
`output/qa/`; it is not an alternate source.

The PDF has a title, English language metadata, bookmarks, content structure tags, and embedded
fonts. The DOCX has native heading styles, list numbering, hyperlinks, English language metadata,
embedded fonts, and continuous column sections. Column reading order follows source order down
the first column and then down the second.

These structural and rendering checks are not certification of PDF/UA compliance or a substitute
for a screen-reader usability review. Microsoft Word and screen-reader testing have not been
performed. Recipient applications may interpret embedded fonts and pagination differently.

## Publication boundary

The local build creates distribution files. The included GitHub Actions workflow builds artifacts
after a future push; it has not been run remotely during this implementation. No website, release,
commit, or push is part of the local build.

## README review

The requested README skill's editorial rubric improved from 12/100 for the title-and-license
stub to 91/100. The largest gain was a verified first-success path and direct navigation to the
individual CV sections. Local links and documented build/check commands were verified.

The remaining optional visual improvement belongs to the screenshot documentation workflow:
add a maintained PDF/student-list preview under the README's existing screenshot markers.
Success would be a legible, current example tied to the generated output, with appropriate alt text.
