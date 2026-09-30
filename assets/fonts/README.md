# Bundled CV fonts

The build uses static TrueType faces to keep PDF and DOCX distribution independent of locally
installed fonts. Assets are downloaded once and committed; normal builds do not download fonts.

The Atkinson families are the Braille Institute typefaces from their upstream font projects.
The Braille Institute download page currently uses an email-and-license form; the upstream
projects provide reproducible static files with explicit redistribution and embedding licenses.
These are upstream releases, not extracted copies of the fonts installed on the author's Mac.

| Family | Faces | Upstream | License notice |
| --- | --- | --- | --- |
| Atkinson Hyperlegible Next | Regular, italic, bold, bold italic | [Next upstream](https://github.com/googlefonts/atkinson-hyperlegible-next) | [OFL-AtkinsonNext.txt](OFL-AtkinsonNext.txt) |
| Atkinson Hyperlegible Mono | Regular | [Mono upstream](https://github.com/googlefonts/atkinson-hyperlegible-next-mono) | [OFL-AtkinsonMono.txt](OFL-AtkinsonMono.txt) |
| IBM Plex Sans Condensed | Regular, italic | [IBM Plex](https://github.com/IBM/plex) | [OFL-IBMPlex.txt](OFL-IBMPlex.txt) |

[provenance.json](provenance.json) records exact revision URLs and SHA-256 checksums. The build
verifies them before rendering and checks embedding permissions. Font obfuscation inside DOCX
uses the standard document font-embedding mechanism; the original font files remain unchanged.
