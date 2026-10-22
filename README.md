# peopleviewer — Flask CRM prototype

A small Python/Flask project originally intended to explore customer records and invoices for product-development work. The tracked implementation is closer to a **Flask application factory and SQLite schema scaffold** than a completed CRM.

## What the source contains

- `__init__.py` — Flask application factory (`create_app`) and a minimal route.
- `db.py` — SQLite connection helpers and database initialization functions.
- `schema.sql` — **user** and **post** tables. The schema drops existing tables during initialization; it does not establish invoice or customer models.
- `start.sh` — an empty file; **not a working startup script**.

## Safe development

Install compatible Flask/Click dependencies in an isolated Python environment after determining supported versions. There is no pinned dependency manifest or verified one-command setup. Inspect `db.py` and `schema.sql` before initializing any database: the schema starts with `DROP TABLE IF EXISTS` statements and can destroy existing test records.

Use a disposable SQLite database and synthetic users. Never place real customer invoices, passwords, account identifiers, tax records, or business contact details in Git or unredacted logs.

## Unimplemented scope

A production CRM needs customer/invoice data models, role-based authentication, password hashing, CSRF protection, backups, export/import rules, tests, and a documented deployment boundary. None is established by this repository snapshot.

**Status:** source-backed documentation; application and tests were not executed.
