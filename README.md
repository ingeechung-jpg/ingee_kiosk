# ingee_kiosk

Static site + publish pipeline.

Structure:
- public/      static site (HTML/CSS/JS)
- data/        generated JSON/Markdown (published from Sheets/Docs)
- scripts/     Apps Script publish tool

Workflow:
1) Edit Google Sheets/Docs
2) Run Apps Script `publishAll()`
3) GitHub receives `data/` updates
4) Static site reads `/data/*.json`
