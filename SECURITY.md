# Security and privacy

DTC-SilverTouch is a **browser-local personal finance tracking tool**, not a hosted accounting database or multi-user service.

## What is stored where?

| Item | Location |
| --- | --- |
| Application HTML / CSS / JavaScript | Public GitHub repository and GitHub Pages |
| Expenses, payments and allocations | IndexedDB in the user's browser |
| Proof screenshots added through the app | The same local IndexedDB |
| JSON backups and CSV/PDF reports | Wherever the user downloads, copies or shares them |

There is **no account login, cloud synchronization, or server-side storage of records** in this version.

## Before entering real financial details

- Verify the custom domain loads with **valid HTTPS**, not only HTTP.
- Use a device and browser profile you control; do not leave an unlocked shared computer logged in.
- Download and securely keep periodic full JSON backups, especially before clearing site data, changing domains, or changing devices.
- Treat the full JSON backup as **sensitive financial data**. It can contain screenshot images encoded in the file.
- Do not share payment references, bank details, payment screenshots or real transaction backups in public GitHub Issues.
- Do not commit backups, statements or screenshots to the repository. `.gitignore` helps avoid accidental commits but cannot remove content previously committed.

## Reporting a security issue

If you discover a vulnerability, please avoid posting exploit details or private financial data in a public issue. Use the repository's **Security** tab / private vulnerability reporting if enabled, or contact the repository maintainer privately through an established channel.

Do not include real credentials, personal transaction files, or sensitive account numbers in a proof of concept.

## Important limitations

GitHub Pages serves a public static app. HTTPS protects data in transit to the hosted website; it does **not** encrypt browser IndexedDB at the application level, provide an account login, or create private cloud storage.
