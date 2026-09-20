# BALAJI AUTOMOBILES — Sales Enquiry & Customer CRM

Hero MotoCorp showroom CRM for enquiries, follow-ups, staff assignment, reports and audit history.

## What you get

- **Owner** and **Staff** roles
- Secure sign-in (Google, X, or email/password)
- Server-side permission checks on every query (staff cannot see another salesperson’s customers by changing a URL or API call)
- Enquiry + follow-up workflow
- Owner dashboards, reports, CSV export, staff management, audit log
- Mobile-first layout, installable as a PWA

This app does **not** use Supabase. It uses the platform Postgres database plus Better Auth. The browser never receives a database key. That is the security boundary.

## How to start

1. Sign in (Google / X, or create the first email owner account if none exists).
2. The first signed-in user becomes **Owner**. Sample (demo) enquiries are loaded automatically so you can try the workflow.
3. Open **Staff** and create salespeople. Copy the one-time password and share it with them.
4. Staff sign in with that email and password. They only see enquiries they created or were assigned.

Demo rows are labelled **Demo**. Do not treat them as real customers.

## Daily workflow

Customer walks in → staff creates enquiry → owner sees it on the dashboard → staff logs follow-ups → status moves to Booked / Sold → owner reads it in reports → every important action is written to audit history.

## Roles

**Owner** — all enquiries, dashboards, reports, exports, audit, staff accounts, settings.

**Staff** — add enquiries, work their own assigned/created records, log follow-ups, mark Sold/Lost on those records. They cannot open reports, audit, staff admin, or another person’s book.

Deactivating a staff account immediately invalidates their sessions.

## Data

Customer records live in Postgres. Access is checked on the server using the signed-in user id from the session — not from anything the browser claims.

## PWA

Use the browser install / Add to Home Screen action. Offline use does not unlock customer data; the app still needs a signed-in session and the server to read records.
