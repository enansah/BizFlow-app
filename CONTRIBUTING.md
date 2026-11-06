# How we work on BizFlow

We follow a simple software development life cycle (SDLC) and a Git Flow style of branching.

## The life cycle

Every feature goes through the same steps:

1. **Plan:** write what the feature does and who uses it. Check it against the prototype and the documentation in `docs/`.
2. **Design:** agree the screens (in the prototype) and any server or data changes.
3. **Build:** write the code on a feature branch.
4. **Test:** test it on a real Android phone, including with the internet off.
5. **Review:** open a pull request into `develop` and check it with the pull request checklist.
6. **Release:** when a group of features is ready, make a release branch, test it, then merge it into `main`.
7. **Maintain:** fix problems found by shops on hotfix branches.

## Branches

| Branch | Comes from | Merges into | Used for |
|---|---|---|---|
| `main` | | | The released app. Never commit to it directly. |
| `develop` | `main` | `main` (through a release) | Finished features waiting for the next release. |
| `feature/<name>` | `develop` | `develop` | One feature, such as `feature/selling` or `feature/momo-prompts`. |
| `fix/<name>` | `develop` | `develop` | A bug found before release. |
| `release/<version>` | `develop` | `main` and `develop` | Final testing for a version, such as `release/1.0.0`. |
| `hotfix/<name>` | `main` | `main` and `develop` | An urgent fix to the released app. |

Name branches in lower case with dashes: `feature/staff-permissions`, not `Feature/StaffPermissions`.

## Planned feature branches

These follow the prototype. Start each one from `develop` when work on it begins.

- `feature/auth`: welcome, owner sign-up, sign-in, PINs, devices
- `feature/selling`: cart, checkout, discounts, parked sales
- `feature/stock`: products, packs and singles, restock and undo, stock count
- `feature/credit`: credit customers and deposits
- `feature/suppliers`: supplier records
- `feature/staff`: staff, permissions (duties), locking
- `feature/receipts`: receipts, SMS and WhatsApp, print stations
- `feature/plans-payments`: plans, trial, limited mode, Paystack plan payments, SMS bundles
- `feature/momo-prompts`: Get paid by MoMo, MoMo prompts at checkout, the MoMo fee setting
- `feature/reports`: home, dashboard, reports, history, Excel export
- `feature/barcodes`: barcode scanning and the shared catalogue
- `feature/offline-sync`: working offline and syncing between devices
- `feature/profile`: profile, your data (download and delete), contact us

## Day-to-day steps

Start a feature:

```bash
git checkout develop
git pull
git checkout -b feature/selling
```

Save work often with small commits:

```bash
git add .
git commit -m "Add discount box at checkout"
git push -u origin feature/selling
```

When it is done, open a pull request from `feature/selling` into `develop` on GitHub. Merge it once the checklist is complete, then delete the branch.

Make a release:

```bash
git checkout develop
git pull
git checkout -b release/1.0.0
```

Test and fix on the release branch. Then merge it into `main`, tag it `v1.0.0`, and merge it back into `develop`.

## Commit messages

- Start with a verb: "Add", "Fix", "Change", "Remove".
- Say what changed in plain words: "Fix receipt total when a discount is given".
- Keep the first line under about 70 characters.

## Keeping things safe

- Never commit passwords, Paystack keys, SMS keys or `.env` files.
- Use Paystack **test** keys in development. Live keys only go on the live server.
- Ghana Card numbers and other personal data never go in test files or screenshots.
