# BizFlow-app
An inventory management app that is used to organise stock, make sales, manage staff duties, contact suppliers of specific stocks and the more.

BizFlow is built for small shops in Ghana: provision stores, cosmetics, chemical shops and similar. It works on a cheap Android phone, keeps selling when the internet is off, and takes MoMo payments.

## What is in this repository

| Folder | What it holds |
|---|---|
| `web/` | The app shops use (React). Phone layout and PC/tablet layout. |
| `server/` | The BizFlow server (Node). Accounts, syncing, SMS, and Paystack payments. |
| `docs/` | The prototype documentation (PDF) and brand files. |
| `docs/prototype/` | Exported versions of the clickable prototype. Open the newest one in a browser. |
| `docs/brand/` | Logo and app icons. |

## Branches

- `main` is the released app. Only tested work is merged here.
- `develop` is where finished features come together before a release.
- Every feature, fix or release gets its own short-lived branch.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full branching and release steps.

## Status

The design is a clickable prototype. The real app in `web/` and `server/` has not been started yet.
