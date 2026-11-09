# SafiriCare

Patient-centred care coordination platform for the Democratic Republic of Congo. Connects patients, community health workers, clinics, hospitals, laboratories and pharmacies in one coordinated care journey. First focus: maternal care, referrals, selected infection follow-up and medication collection.

Inspired by Kivra: every patient has a secure health inbox. Patients without smartphones are supported through community workers.

## Status

**Phase 1 (this repository): public website and interactive prototype.**

| What works today | Planned (later phases) |
|---|---|
| Bilingual public website (EN / FR) with language switch | Django backend with role-based access |
| Interactive care journey prototype (7 steps, fictional patient) | PostgreSQL database |
| Six platform roles explained | HL7 FHIR interfaces (OpenMRS, DHIS2, lab and pharmacy systems) |
| Mobile-first, works on slow connections | Offline mode with sync status |
| Donor and partner section with contact | Infection tracking and aggregate reporting |
| | Pilot preparation: security audit, clinical approval, staff training |

All data in the prototype is fictional. No real patients, no credentials, no confidential documents.

## Project structure

```
safiricare/
├── index.html          Public website + interactive prototype (single file)
├── README.md           This file
├── LICENSE             To be agreed (open-source release planned)
├── .gitignore
└── docs/
    ├── architecture.md Proposed technical architecture for Phase 2
    ├── care-journey.md The 7-step care journey in detail
    └── setup.md        How to run and deploy the website
```

## Running the website

No build step. Open `index.html` in any browser, or serve it locally:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000

## Tech stack (Phase 1)

HTML5, CSS3, vanilla JavaScript. No framework, no dependencies, no build tools. Fonts from Google Fonts (Inter, Playfair Display). Works on inexpensive smartphones and slow connections.

## Tech stack (Phase 2, proposed)

Python / Django backend, PostgreSQL, HL7 FHIR interfaces, role-based access control, encryption at rest and in transit, access logs, backups and tested recovery. See `docs/architecture.md`.

## Ownership and licence

Developed for SafiriCare (registered NGO, DRC and Sweden). Repository is private until an open-source licence is agreed. Never commit patient data, passwords, access keys or confidential documents.

## Developer

Luna Amanuel, 2026.
