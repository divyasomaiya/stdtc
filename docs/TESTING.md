# Manual testing checklist

Use a **separate browser profile or other isolated test environment** containing no real records, or make a verified backup before loading demo data. The built-in **Load Delhivery & Jio Test Scenario** replaces the current browser dataset.

## Core transaction checks

- [ ] Add a ₹500 Delhivery expense using personal money.
- [ ] Record ₹1,500 received: ₹500 allocated as reimbursement, ₹1,000 reserved for Delhivery.
- [ ] Add a ₹200 personal Jio expense; verify pending = ₹200 and Delhivery advance = ₹1,000.
- [ ] Add a ₹300 Delhivery expense from reserved advance; verify pending = ₹200 and advance = ₹700.
- [ ] Reimburse ₹200 through Salary Adjustment; verify pending = ₹0 and advance = ₹700.
- [ ] Test partial reimbursement of an expense and verify the remaining amount.
- [ ] Choose Other category, add an optional description, and confirm it appears in history, CSV and report.
- [ ] Verify money for one company/purpose cannot be silently used by another.

## User interface

- [ ] Check both expense and received-money modals at 100% desktop browser zoom.
- [ ] Check that Save and Cancel stay reachable with long forms and on mobile screens.
- [ ] Test scrolling without inadvertently scrolling the background page.
- [ ] Test wide transaction tables on mobile.
- [ ] Test A4 portrait compact report and A4 landscape detailed report for clipping.

## Saving and backup

- [ ] Save a test record, refresh, and confirm it remains visible.
- [ ] Close and reopen the browser at the **same website origin**, then confirm the record remains.
- [ ] Export a full JSON backup and independently confirm the downloaded file exists.
- [ ] Restore a **copy** of a known-valid V1.0 backup; compare record counts, totals, linked reimbursements and screenshots.
- [ ] Try an invalid backup and confirm the existing data is not replaced.
- [ ] Test CSV export and check the monetary columns remain numeric in Excel.
- [ ] Keep an independent copy of production backups before testing any code update.

These checks are intended to be performed after each release; they are not a claim that every device or browser has already passed.
