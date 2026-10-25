*Report it. Understand it. Resolve it.*

CampusPulse AI is a smart campus problem solver. Students report issues such as Wi-Fi outages, water leaks, overflowing dustbins, broken lights and damaged equipment. Administrators organize, prioritize, track and resolve them. It was built as a hackathon MVP.

## The problem

Campus problems often go unreported, get lost in chat groups, or are reported several times by different people. Administrators have no single prioritized queue, and students cannot see what happened to their report.

## Features

| Feature | What it does |
|---|---|
| Issue reporting | Form with title, description, location and category. Required fields are validated, and "Saved" is shown only after a successful save. |
| AI issue analysis | Suggests category, priority with reason, responsible department and recommended next action. |
| Safety handling | Safety-related reports are flagged for prompt human review. Analysis is a suggestion, never a resolution. |
| Duplicate detection | Matches on title and description words, location and category, and suggests similar open reports before submitting. Nothing is merged, deleted or rejected automatically. |
| Student dashboard | Search, filter by category, status and priority, and a detail view with analysis and status history. |
| Admin dashboard | Totals for all, pending, in-progress and resolved issues, a category chart and a 7-day trend, all calculated from the records shown. |
| Status tracking | Pending, In Progress and Resolved, with a logged history and optional resolution notes. |

Issue categories: Maintenance, Internet/Wi-Fi, Sanitation, Electrical, Plumbing, Safety, Other.
Priorities: Low, Medium, High, Critical.

## How to try it (about two minutes)

1. Open **Report** and describe a problem. Watch for the similar-reports warning as you type.
2. Submit it and read the analysis.
3. Open **Issues** to find it, then try search and filters.
4. Open **Admin** to see the dashboard. If you have admin access, update the status and add a resolution note.

## Honest status

### Fully working
- Form validation, loading states and error messages
- Search and filters
- Dashboard numbers, calculated from the records shown
- Duplicate suggestions
- Status history

### Depends on the claude.ai platform
- **Saving across refreshes** uses the claude.ai built-in database.
- **Real AI analysis** is requested through the platform, so no API key is in the page.
- **Admin controls** appear only for the page owner or editors, based on the platform's sign-in.

### Demo data and rule-based logic
- Four sample issues are labeled **DEMO** and can be switched off with the "Include demo samples" checkbox. Status changes on them are not saved.
- When AI is unavailable, analysis falls back to simple keyword rules. It is clearly labeled "Demo rule-based analysis (not AI)".

## Running it outside claude.ai (for example GitHub Pages)

The app is a single file, `index.html`, with no build step. Open it in a browser or host it with GitHub Pages. Outside claude.ai:

- Reports are kept in memory only and disappear on refresh. A banner says so.
- Analysis uses the keyword rules, labeled as not AI.
- Admin status controls do not appear, because there is no sign-in.
- Search, filters, duplicate detection and dashboard calculations still work.

## Limitations

- **Admin permissions are enforced in the interface only.** The platform database does not separate students from admins, so a real deployment needs a backend with proper roles.
- **Image attachments are not supported.**
- **Reports are visible to everyone with access** to the app. Do not use it for real campus data in this form.
- **Duplicate detection is word-overlap based**, not semantic, so it can miss differently worded reports.

## What a production version would need

- A backend and database (for example Node.js with a hosted database)
- Real authentication, with separate student and administrator roles
- A server-side AI endpoint that keeps API keys off the client
- Image upload and storage
- Notifications when a status changes

## Tech

- Single-file HTML, CSS and vanilla JavaScript
- claude.ai artifact runtime for database, sign-in and AI sampling

## Author

Built by Chindada Anand Teja,Karri Devi Harshith Prudhvi, B.Tech CSE, KL University.
