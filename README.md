# Ashiesh Enterprises — Costing Calculator & Die Registry

A browser-based tool for EVA/foam product costing, kit assembly, order tracking, and a company-wide die registry — no installation needed, works straight from a web page.

**Live tool:** https://divyaanshikaushik.github.io/ASHIESH-ENTERPRISES/

## What's inside

- **🧮 Calculator** — step-by-step product costing (sheet sizing, shots-per-sheet, patta cutting, Hydraulic Clicker vs. CNC) with mm/inch support
- **🧩 Assembly Builder** — combine multiple costed pieces into multi-component kits
- **📋 Order Board** — Kanban-style order tracking across six stages, filterable by party
- **🗂️ Die Registry** — one record per physical die: which client(s) and product(s) it's used for, size, material, die cost, per-unit product cost, status, and photos of both the die and the finished product
- **🔄 Company-Wide Sync** — the Die Registry is shared live across everyone who opens this link, backed by a Google Sheet + Google Drive (for photos). No login, no manual setup — it connects automatically.

## How it works

This is a single self-contained HTML file (`index.html`) — everything (styling, logic, calculations) lives in one page. It's hosted for free via [GitHub Pages](https://pages.github.com/), which serves this repo's `index.html` at the live link above.

The Calculator, Assembly Builder, and Order Board save data locally in your browser (per device). The Die Registry is different — it syncs to a shared Google Sheet via a small Google Apps Script backend, so every teammate who opens the live link sees the same dies, in real time.

## Updating the tool

To change anything (fix a bug, add a feature):

1. Edit `index.html` directly on GitHub (pencil/edit icon), or edit a local copy and paste the updated code in
2. Commit the change — GitHub Pages redeploys automatically within a minute or two
3. Reload the live link to see the update

## Updating the shared Die Registry backend

The sync backend is a Google Apps Script (`DieRegistry_AppsScript.gs` — kept separately, not deployed to this repo) attached to a Google Sheet. If you need to change how die data is stored or add new fields:

1. Open the Google Sheet, go to Extensions → Apps Script
2. Edit the script, save
3. Deploy → Manage deployments → edit the existing deployment → select **New version** → Deploy (this step is easy to miss — without it, the live URL keeps serving the old script code)

## Notes

- The repo is public (required for free GitHub Pages), so treat the sync link as semi-private — anyone with it can read/write the die registry, there's no login screen
- Photos are auto-compressed before upload and stored in Google Drive, not directly in the Sheet, to avoid hitting cell size limits
- If the Company-Wide Sync box ever shows "Could not reach the shared registry," it usually means the tool was opened as a local file instead of through the live link above — always use the `https://` link, not a downloaded copy
