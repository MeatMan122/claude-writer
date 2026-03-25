---
description: Export your manuscript to .docx, .epub, .pdf, or .html
argument-hint: [format]
---

Find the story project directory in the user's workspace. Compile all chapter files from the `chapters/` directory into a single manuscript.

The user may specify a format as an argument: $ARGUMENTS

Supported export formats:
- **docx** — Microsoft Word document (use python-docx)
- **epub** — E-book format (use pandoc if available, or ebooklib)
- **pdf** — PDF document (use pandoc or weasyprint)
- **html** — Single HTML file with styling
- **md** — Single consolidated Markdown file

If no format is specified, ask the user which format they'd like.

Export process:
1. Read all chapter files in order (chapter-01.md, chapter-02.md, etc.)
2. Compile into a single document with:
   - Title page (story title from PROJECT.md)
   - Table of contents
   - Chapter breaks with titles
   - Consistent formatting
3. Save the exported file to the user's workspace
4. Present the file to the user

For Markdown source, chapter files are already in .md format — just concatenate them with proper chapter headings.

For other formats, first check if pandoc is available (`which pandoc`). If so, use pandoc for conversion. If not, use Python libraries appropriate to the format.
