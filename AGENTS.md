# Repository Guidelines

## Project Structure & Module Organization

This repository currently contains spreadsheet-style data files rather than application source code.

- Root directory: primary datasets, including `sk_hynix_naver_jokes.csv`, `.xls`, and `.xlsx` variants.
- `Test10/`: duplicate or working-copy versions of the same dataset family.
- `AGENTS.md`: contributor guidance for future edits.

Keep related dataset exports together and preserve the shared base name across formats, for example `name.csv`, `name.xls`, and `name.xlsx`.

## Build, Test, and Development Commands

There is no build system or package manager configured. Use simple file validation commands before submitting changes:

- `Get-ChildItem -Recurse`: list repository contents.
- `rg --files`: confirm tracked-style file layout quickly.
- `Import-Csv .\sk_hynix_naver_jokes.csv | Select-Object -First 5`: inspect CSV headers and sample rows in PowerShell.

When editing spreadsheets, export CSV copies when possible so changes can be reviewed with text-based tools.

## Coding Style & Naming Conventions

No source-code style rules are currently defined. For repository files:

- Use lowercase snake_case filenames, matching the existing pattern: `sk_hynix_naver_jokes_fest_mode.csv`.
- Avoid spaces, punctuation-heavy names, and date formats that sort poorly.
- Keep CSV headers stable unless the schema change is intentional.
- Use UTF-8 for CSV files where possible.

If scripts are added later, place them in a dedicated `scripts/` directory and document their commands here.

## Testing Guidelines

No automated tests are present. Validate data changes manually before committing:

- Open CSV files and confirm headers are present.
- Check that row counts match expectations across `.csv`, `.xls`, and `.xlsx` exports.
- Verify spreadsheet files open without repair prompts.

If automated checks are introduced, prefer small scripts that validate schema, encoding, duplicate rows, and required columns.

## Commit & Pull Request Guidelines

This directory is not currently initialized as a Git repository, so no local commit history is available. Use clear, imperative commit messages if Git is added, such as:

- `Add fest mode dataset export`
- `Normalize CSV column names`

Pull requests should include a short summary, list changed files, explain any schema or row-count changes, and attach screenshots only when visual spreadsheet formatting is relevant.

## Security & Configuration Tips

Do not commit credentials, private exports, or personal data. Before adding new spreadsheets, review hidden sheets, comments, formulas, and metadata that may expose sensitive information.
