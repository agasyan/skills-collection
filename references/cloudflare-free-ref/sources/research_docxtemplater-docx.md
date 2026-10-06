# Word Files: docxtemplater and docx
docxtemplater (2026). https://docxtemplater.com/ · repo `open-xml-templating/docxtemplater` (MIT or GPLv3, pushed 2026-09-21). docx (2026). https://docx.js.org/ · repo `dolanmiu/docx` (MIT, 5.9k stars, pushed 2026-10-06)
Type: docs · Read: 2026-10-06

## What it says
- **docxtemplater** "generates Word (`.docx`), PowerPoint (`.pptx`), Excel (`.xlsx`) and OpenDocument (`.odt`) documents from templates filled with structured data such as JSON". It runs in Node and the browser.
- **Free core:** tags `{user}`, loops `{#users}{name}{/}`, and conditions; "The open-source core supports only DOCX and PPTX." License: "dual licensed … MIT license *or* the GPLv3".
- **Paid modules:** images, HTML, charts, tables, xlsx templating, styling, subtemplates, and more. No PDF conversion.
- **docx** generates `.docx` in code, in the browser or Node: tables, headers and footers, images, page numbering, styles. `Packer.toBlob` makes a browser download.

## For an internal system
- Let staff design the invoice in Word with `{tags}`; the system fills it with docxtemplater. They keep using the tool they know.
- Use docx when there is no Word template and the layout lives in code.
