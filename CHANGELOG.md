# Changelog

Changes for DTC-SilverTouch are documented here.

## [1.1.0] — November 2026

Updated the existing V1.0 single-file application while keeping the same local database and V1.0-compatible JSON backup format.

### Added
- Responsive mobile-height forms with an accessible scrollable content area and visible Save / Cancel actions.
- A choice between compact A4 portrait and detailed A4 landscape print layouts.
- Optional `categoryDetail` input when the expense category is **Other**.
- More explicit browser-storage status messaging and backup validation checks.

### Improved
- Modal background-scroll handling, touch targets, and narrow-screen layout.
- Error handling for IndexedDB persistence before confirming successful saves.
- JSON backup validation and a preview before replacing local data.
- CSV export support for the optional category detail.

### Compatibility
- Continued use of `DTC_SilverTouch_DB`, object store `app_data`, and key `MAIN_STATE`.
- Support for V1.0 JSON backups with `backupFormatVersion: 1`.
- Existing expense/receipt IDs, allocations, advance purposes and screenshot references are preserved on compatible restore.

## [1.0.0] — November 2026

### Initial release
- Personal and company-advance expense recording.
- Received money, reimbursement allocations and advance buckets by company/purpose.
- Dashboard with expenses, received amounts, outstanding reimbursement and available advance.
- Date-filtered accountant reports, CSV download, print/save-as-PDF and WhatsApp summary.
- Browser IndexedDB saving and manual JSON backup/restore including proof screenshots.

> The descriptions above reflect features present in the source. A release note is not a substitute for testing the app with a safely backed-up sample database.
