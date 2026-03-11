# Publish Script (Sheets/Docs -> GitHub)

This Apps Script reads your Google Sheets/Docs and publishes JSON/Markdown files into your GitHub repo.

## 1) Setup
1. Open Google Apps Script (standalone) and paste `publish.gs`.
2. Fill `CONFIG` values:
   - `SPREADSHEET_ID`
   - `GITHUB_OWNER`
   - `GITHUB_REPO`
   - `GITHUB_BRANCH`
   - `GITHUB_TOKEN` (classic token with repo access)

## 2) Sheet structure (header-based)
- **Profile**: columns like `Name`, `Email`, `Instagram`, `Website`
- **Courses / Projects / Exhibitions**: columns like `Title`, `Year`, `Code`, `Location`, `Link`, `Pass`, `Show`, `Publish`
- **Note**: columns like `Title`, `Year`, `Text(마크다운문서)`, `Pass`, `Show`, `Publish`

Text column can be:
- Markdown text directly, or
- Drive file URL to a `.md` file

## 3) Run
Run `publishAll()`.
It writes:
- `data/dashboard.json`
- `data/sections/*.json`
- `public/data/notes/*.md`

## Notes
- Password protection is **client-side** in static mode (visible in JSON). Do not use for secrets.
- Drive links must be shared "Anyone with the link" if you reference files.
