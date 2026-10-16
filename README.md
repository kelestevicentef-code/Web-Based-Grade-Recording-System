# FAR EASTERN POLYTECHNIC COLLEGE — Grade Recorder

A **Web-Based Grade Recording System** prototype for Far Eastern Polytechnic College
(Brgy. Sta. Lucia, DB81, Dasmariñas City, Cavite), built for **S.Y. 2026–2027, First Semester**.

> **This is a front-end prototype / visual mockup.** It has **no backend**, no database and
> no network requests of any kind. Every number, name and table row is hard-coded in the HTML,
> and the login screen accepts any input. It exists to demonstrate the interface and the flow
> between the four user roles.

## Tech stack

Plain **HTML + CSS + vanilla JavaScript**. No frameworks, no build step, no npm install,
no CDN links and no external dependencies whatsoever — the pages open directly in a browser.
The only JavaScript is small inline `<script>` blocks for the login redirect, the role guard,
the toast messages and the auto-compute calculation.

## Running it

Just open `index.html` in a browser. Or, to serve it locally (recommended, so relative
links and the browser history behave exactly like a hosted site):

```bash
python3 -m http.server 3000
# then visit http://localhost:3000/
```

Deploying to **GitHub Pages** works as-is — this folder is the site root, there is nothing to build.

## Demo accounts

On the login page (`index.html`) enter **any** username and **any** password, then pick a role:

| Role | Lands on | Signed-in user |
| --- | --- | --- |
| Teacher | `teacher-dashboard.html` | Mark Villanueva |
| Administrator | `admin-dashboard.html` | Lorna Bautista |
| Student | `student-portal.html` | Juan Dela Cruz |
| Parent / Guardian | `parent-portal.html` | Roberto Dela Cruz |

The chosen role is kept in `sessionStorage` and each page runs a small guard, so a student
who opens the teacher URL is bounced back to their own portal (and vice-versa).

## What each page shows

- **`index.html`** — school header with the seal, login card, role selector.
- **`teacher-dashboard.html`** — **Practical Research 2 — Grade 12 – Aquarius** (7 students):
  AI-Powered Academic Insights, class statistics, **Manage Scores** with a working
  *Auto-Compute* (final grade = average of Quiz 1 and Quiz 2, colour-coded pass/fail),
  attendance record, and PDF material upload/share (mockup).
- **`student-portal.html`** — Juan Dela Cruz's own first-quarter grades across the four
  subjects, attendance summary, progress tracker and notifications. Read-only.
- **`parent-portal.html`** — the same child's academic record from the guardian's side:
  grades, attendance, and email-alert settings with an alert history.
- **`admin-dashboard.html`** — school-wide overview, teacher accounts, student accounts,
  class sections and the activity log.

### Section and subjects used throughout

- Section: **Grade 12 – Aquarius** (sibling sections: G12 – Libra, Sagittarius, Capricorn)
- **Practical Research 2** — Mark Villanueva (adviser)
- **Contemporary Philippine Arts from the Regions** — Grace Fernandez
- **Understanding Culture, Society and Politics** — Divina Ocampo
- **Physical Education** — Rogelio Panganiban

Every subject's teacher is consistent across the student portal, the parent portal and the
admin teacher table, and the general average (84.0) matches the four final grades.

## Files

```
index.html               Login page + role-based redirect
teacher-dashboard.html   Teacher: insights, scores, attendance, materials
student-portal.html      Student: own grades, attendance, progress, notifications
parent-portal.html       Parent/guardian: child's record and alerts
admin-dashboard.html     Administrator: overview, accounts, sections, activity log
style.css                The entire design system (FEPC green + golden yellow)
logo.svg                 School seal (vector reconstruction)
```

## Prototype scope / limitations

- No real authentication, no persistence — refreshing a page resets everything.
- Buttons such as *Upload PDF*, *Edit* and *Add Teacher* show a confirmation toast instead of
  performing the action; this is stated in the UI where relevant.
- All data is static sample data for one section.
- `logo.svg` is a hand-built vector reconstruction of the college seal, not the official artwork.
- The wide grade tables scroll horizontally inside their own container on narrow screens so the
  page never overflows.
