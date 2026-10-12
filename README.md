# AliExpress PDF Invoice

Automatically download PDF invoices for your AliExpress orders.

The goal is a repeatable tool that retrieves the original invoice PDFs without manually navigating every order in a browser.

## Status

Project initialization. No downloader is implemented yet, and no invoice retrieval endpoint or authentication flow has been verified.

## Intended workflow

1. Authenticate with your own AliExpress account, keeping credentials and session data local.
2. Find orders within a chosen date range.
3. Retrieve available original invoice PDFs.
4. Save invoices with stable filenames and skip files already downloaded.
5. Report downloaded, unavailable, and failed invoices so interrupted runs can resume.

## Investigation plan

- Inspect invoice requests made by an authenticated AliExpress session to establish how the original PDFs are retrieved.
- Determine which requests can be reproduced directly and which steps require an interactive browser session.
- Build a minimal command-line proof of concept for downloading one invoice before implementing order discovery and batch downloads.
- Validate PDF responses, session expiry handling, duplicate detection, and retry behavior.

Direct authenticated requests are a candidate approach, not a confirmed solution. Interactive login or verification may still be necessary. The tool should clearly report when user interaction is required.

## Local data

Credentials, cookies, browser profiles, request captures, order exports, and invoices must stay out of this public repository. Use the ignored `private/`, `data/`, `invoices/`, or `downloads/` directories for local account data. Never include account data in issues or example files.

The repository includes ignore rules for common sensitive files. Review every staged change before committing; ignore rules cannot identify every form of personal data.
