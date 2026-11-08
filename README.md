# DocPeek

**See what your document says about you before you send it.**

Drop a `.docx`, `.xlsx`, `.pptx` or `.pdf` and DocPeek shows what is hidden inside:

- your name in "Author" and "Last saved by", company, template path
- total editing time, how many times the file was saved, dates
- hidden text, white text, 1-pt text (Word)
- invisible characters: zero-width spaces, joiners and similar
- tracked changes and comments that are still in the file
- hidden sheets and cell comments (Excel), speaker notes and hidden slides (PowerPoint)
- author, title, app and dates in PDF metadata

For Office files it can download a copy with the name, company and editing time removed.

**Live:** https://econnx.github.io/docpeek/

## Privacy

Everything runs in your browser. The file is never uploaded anywhere.
It is one HTML file, so you can read all the code in `index.html`.

## Run locally

Open `index.html` in a browser. That's it.

## How it works

`.docx`, `.xlsx` and `.pptx` files are zip archives full of XML. DocPeek unzips them with
[JSZip](https://stuk.github.io/jszip/) and reads `docProps/core.xml`, `docProps/app.xml`
and the content parts. For PDFs it reads the Info dictionary and XMP metadata.

Limits: text inside compressed PDF streams is not checked for invisible characters,
and photo EXIF data inside documents is only counted, not read.

## License

MIT
