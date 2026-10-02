# Public Update Notes

## 2026-10-02 — Reliable competitor monitoring pipeline

Reworked public-catalogue collection and reporting around dated snapshots, explicit currency normalization, preserved unknown availability and bounded partial scans. Repeated collection no longer erases same-day history, while incomplete scans cannot turn missing products into claimed sales. A recoverable publishing process reconciles historical snapshots with a management dashboard; interactive summaries use the same analysis.

The resulting reports separate observed catalogue changes from possible sales and show shared products, price differences and brand coverage. Adapter fixtures, publishing checks and deployed read-only report requests passed. Some sources still reject or fail public requests; these are reported as incomplete rather than claimed as fully monitored. No private source, credentials or operational records are published.


## 2026-09-29 — Independent inventory sources

- Separated branch quantities from supplier availability in spreadsheet-driven inventory updates.
- Made out-of-list clearing explicit and source-specific, protecting stock held by other locations.
- Added dated snapshot reconciliation, duplicate invoice protection, and sale/refund allocation tracking.
- Held ambiguous legacy balances for operator review rather than inventing warehouse ownership.
- Verified 26 synthetic inventory checks, 29 set/workbook regressions, and eight full WordPress worker checks against temporary unpublished fixtures.
- No production records, operational identifiers, credentials, or private source code are included.

## 2026-06-08

- Added a public-safe update note for persistent per-run reporting in spreadsheet-driven commerce operations.
- Highlighted the operational value: reports remain tied to the exact upload/run instead of being overwritten by later uploads.
- Documented cleanup ownership at a high level, keeping private file paths, production exports, and customer data out of the showcase.

## 2026-06-04

- Created a sanitized public showcase for commerce automation and workflow architecture.
- Added employer-facing notes for n8n-style workflow design, CRM routing, reporting pipelines, and safe operational automation.
- Documented the privacy boundary: no production exports, credentials, raw customer data, or private workflow internals are public.
