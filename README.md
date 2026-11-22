# DTC-SilverTouch

**Personal Expense, Company Advance & Reimbursement Tracker**

A lightweight, offline-first web application for tracking business expenses paid personally, reimbursements received from an accountant, and advance funds reserved for future company spending.

**Version:** `1.1.0` · **Built with:** HTML, CSS & vanilla JavaScript · **Storage:** Browser IndexedDB · **Backend:** None

**Live website:** [dtcst.clickworthybydtc.in](https://dtcst.clickworthybydtc.in/)  
**Source:** [divyasomaiya/stdtc](https://github.com/divyasomaiya/stdtc)

> **Important:** Your financial records stay in the browser where you enter them; the website does **not** synchronize transactions across devices. Download JSON backups regularly. Use the hosted site only once its HTTPS certificate is active and your browser shows a secure connection.

## What it does

| Feature | Description |
| --- | --- |
| Expense tracking | Record office expenses paid using personal funds or a company advance. |
| Reimbursements | Log money received, allocate it to expenses, and track partial or full settlements. |
| Reserved advances | Keep company advances separate by company and purpose, without automatic deductions. |
| Transaction history | Search and filter transactions by company, date, and status. |
| Payment proofs | Attach optional JPG, PNG, or WebP screenshots (up to 3 MB each). |
| Accountant statements | Print compact A4 portrait or detailed A4 landscape reports; save as PDF in the browser print dialog. |
| Excel-compatible exports | Download statements as `.csv` files for Excel. This is CSV, **not** native `.xlsx`. |
| WhatsApp summary | Copy a concise financial statement to share with your accountant. |
| Backup and restore | Export and import complete JSON backups, including attached screenshots. |

### Example: reimbursements and reserved funds

1. You spend **₹500** of your own money on Delhivery.
2. Your accountant transfers **₹1,500**: ₹500 reimburses that expense and ₹1,000 becomes a **Delhivery-only advance**.
3. You personally spend **₹200** on the company Jio number. The Delhivery advance remains untouched, and ₹200 is pending reimbursement.
4. You spend **₹300** from the reserved Delhivery advance. The remaining advance is **₹700**, while the Jio reimbursement is still **₹200** pending.

The app keeps *money owed to you* separate from *company advance money you hold*.

## Get started

### Use the hosted app

Open **[DTC-SilverTouch](https://dtcst.clickworthybydtc.in/)** in a modern browser after the GitHub Pages custom domain has working HTTPS. Add an expense or record a reimbursement using the two main buttons.

### Use the app locally

Download `index.html` and open it in a modern browser. The app is a self-contained HTML file; it does not need Node.js, npm, Firebase, or an internet connection for its core functionality.

> Browser storage behavior for `file://` pages varies by browser and file location. For routine use, use one consistent HTTPS address (or a stable local origin) and retain external JSON backups.

### Move existing data into the hosted website

1. On your **old** local copy, open **Backup & Restore → Download Full Backup (.JSON)**.
2. Keep a separate copy of that JSON file somewhere private.
3. Open the **new** hosted website and choose **Backup & Restore → Restore Backup File**.
4. Review the preview carefully. Restoring **replaces** the destination browser's existing records; it does **not** merge records from two devices.
5. Confirm the restore, then compare expense counts, received payments, pending reimbursements, advance balances, and proof screenshots.

V1.1 can read V1.0-format backups (`backupFormatVersion: 1`), with the optional `categoryDetail` field treated as empty when absent.

## Accountant reports

Use **Accountant Reports** to select a date range and company, then choose one of the following:

- **Compact (A4 Portrait):** a short statement with expenses, reimbursements, advances, and closing balances.
- **Detailed (A4 Landscape):** a wider ledger with transaction details and IDs.
- **Print / Save as PDF:** opens the browser print dialog; choose **Save as PDF** as the destination.
- **Export Excel CSV:** downloads numeric amounts in an Excel-compatible CSV file.
- **Copy Summary Text:** copies a plain-text summary suitable for WhatsApp.

The app's amounts are represented internally as **integer paise** to avoid ordinary floating-point rounding issues.

## Data storage, privacy and limitations

- **Local storage:** Transactions, reimbursement allocations, company balances, settings and optional screenshot proofs are stored in **IndexedDB** in your browser.
- **Not cloud sync:** GitHub Pages hosts the application's source files, **not** your transactions. A different device or browser will not automatically show your existing data.
- **Backups are essential:** Clearing browser/site data, using private browsing, a browser storage failure, or changing the site's origin can make local records unavailable.
- **Public source ≠ public records:** Publishing this repository exposes the website's source code; it does not itself upload your browser's IndexedDB data. Anyone using your unlocked browser profile may, however, have access to locally stored records.
- **No account login or server-side access control:** Do not treat the public website as a secure shared accounting platform.
- **No server-side PDF conversion:** PDF creation relies on browser printing.

**Never commit** actual backups, payment screenshots, receipts, financial statements or confidential business information to this repository.

## Repository structure

```text
stdtc/
├── index.html           # Complete V1.1 application
├── CNAME                # GitHub Pages custom domain
├── README.md            # Project overview and usage
├── CHANGELOG.md         # Version history
├── SECURITY.md          # Privacy and security guidance
├── .gitignore           # Prevents accidental commits of local exports
├── .nojekyll            # Serve this static site without Jekyll processing
└── docs/
    ├── DEPLOYMENT.md    # GitHub Pages and DNS instructions
    └── TESTING.md       # Manual verification checklist
```

See [Deployment instructions](docs/DEPLOYMENT.md) and [Testing checklist](docs/TESTING.md).

## Project history

See [CHANGELOG.md](CHANGELOG.md) for details of V1.1 and the original V1.0 feature set.

## Contributing and licensing

This project is currently maintained as a small, single-file application. Bug reports and suggestions can be filed in GitHub Issues **without attaching real transaction data**.

**License:** No open-source license has been selected or included. Publicly visible source code is not automatically granted an open-source license. A license can be added later if the maintainer chooses to permit reuse or distribution.
