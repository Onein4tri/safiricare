# SafiriCare

SafiriCare is a platform that helps patients in the Democratic Republic of Congo get the right care at the right time. It connects patients, community health workers, clinics, hospitals, laboratories and pharmacies, so everyone involved in one patient's care can see what has happened and what comes next. The first focus is care for pregnant women, referrals, follow-up of selected infections and collection of medication.

The idea is inspired by Kivra (the Swedish app where people receive their official mail in one secure digital mailbox). In the same way, each SafiriCare patient gets a secure health inbox with appointments, referral updates, results and prescriptions. Patients without a smartphone are helped by a community health worker.

## What is in this repository

| File | What it is |
|---|---|
| `index.html` | The website and the clickable prototype, all in one file |
| `README.md` | This page |
| `care-journey.md` | The 7 steps of the care journey, explained in a table |
| `architecture.md` | The technical plan for the next phase (for developers) |
| `setup.md` | How to edit and publish the website (for developers) |

## How to open the website

Download `index.html` and double click it. It opens in your web browser. Nothing needs to be installed. It works on a computer and in the browser of a phone.

## What works today (Phase 1)

- **The public website in English and French.** A button at the top right switches the language.
- **A clickable care journey.** In the section "Follow one patient's journey", press "Next step" to walk through the 7 steps with a fictional patient.
- **The six roles explained.** Patient, community worker, clinic or hospital, laboratory, pharmacy, coordinator.
- **A section for donors and partners.** The contact email is still to be added.
- **Mobile first.** (The page adjusts itself to a small phone screen. It is still a website that opens in the phone's browser. It is not an app to install.)
- **Works on slow connections.** (The whole site is one small file, so it loads quickly even on weak internet.)

Everything shown in the prototype is fictional. There are no real patients, no passwords and no confidential documents in this repository.

## What is planned (later phases, from the development brief)

Each item gives the technical name first, then what it means in plain words.

- **Django backend.**
  (The engine room of the application: the part on a server that stores the information and applies the rules. Django is a free, well known toolkit for building this, written in the Python programming language.)
- **PostgreSQL database.**
  (The secure filing cabinet where all records are kept.)
- **Role-based access control.**
  (Each person sees only what their job needs. A pharmacist sees the prescription, and does not see the whole medical file.)
- **Encryption at rest and in transit.**
  (The information is scrambled so only authorised people can read it, both while it is stored and while it travels over the internet.)
- **Access logs.**
  (A record of who opened or changed which information, and when.)
- **Backups and tested recovery.**
  (Safe copies of all data, and a tested way to bring everything back if something breaks.)
- **HL7 FHIR interfaces.**
  (FHIR, pronounced "fire", is an international standard format for health information. It lets SafiriCare exchange information with systems that clinics already use: OpenMRS, a patient record system, DHIS2, the health statistics system used by many health ministries, and laboratory and pharmacy systems.)
- **Offline mode with sync status.**
  (Health workers can keep working without internet. The information is sent when the connection comes back, and the screen shows whether it has been sent.)
- **Infection tracking.**
  (For each patient, the steps are kept apart: suspected, tested, confirmed by a clinician, treated, followed up. One step is never mistaken for another. For example, collecting medicine does not mean the patient has recovered.)
- **Aggregate reporting.**
  (Summary numbers for authorised teams, for example how many cases in a district this month, without showing who the patients are.)
- **Pilot preparation.**
  (Before real patients use it: a security audit, where independent experts look for weaknesses. Clinical approval, where doctors and nurses confirm that the steps match safe medical practice. Staff training for the people who will use it.)

## How the Phase 1 website is built

- **HTML, CSS and JavaScript.**
  (The three standard languages of every website. HTML is the content, CSS is the appearance, JavaScript is the behaviour, such as the language button.)
- **No dependencies and no build tools.**
  (The site needs no extra software and no installation. It is one file that opens directly.)
- **Google Fonts: Inter and Playfair Display.**
  (The two typefaces on the page. Inter is used for normal text and Playfair Display for headings. Google Fonts is a free library of typefaces. Without internet the browser uses a standard typeface and everything still works.)

## Where the content comes from

**From SafiriCare's development brief:** the purpose, the two parts (website and application), English and French, the Kivra idea, the 7 step care journey, the six roles and what each one does, the infection tracking rules, the technical wishes (Python and Django, PostgreSQL, HL7 FHIR, OpenMRS, DHIS2), the privacy and security requirements, the GitHub rules and the project stages.

**Added by the developer:** the design (colours, typefaces, layout), the wording on the website and its French translation, the fictional patient story used in the prototype, the summary "how it works" in 4 steps, the three cards in the donor section, and the technical details in `architecture.md`.

**To be checked by SafiriCare before partners see it:** the French text (by a French speaker), the fictional medical example (by a clinician), the exact official wording about registration and validation, and the contact email.

**Statistics:** the page uses one number, with its source: 547 maternal deaths per 100,000 live births in the DRC (2020 estimate), from WHO, UNICEF, UNFPA, World Bank Group and UNDESA, "Trends in maternal mortality 2000 to 2020" (2023).

## Ownership and licence

Developed for SafiriCare. The repository is private until an open-source licence is agreed. Patient data, passwords, access keys and confidential documents are never stored here.

## Developer

Website and prototype developed by Luna Amanuel, 2026.
