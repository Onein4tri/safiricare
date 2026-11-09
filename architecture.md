# Proposed architecture (Phase 2)

This document describes the planned technical architecture for the SafiriCare application. Nothing here is built yet. Phase 1 (this repository) is the public website and prototype only.

## Overview

```
[ Patient phone / SMS ]   [ Community worker app ]   [ Clinic / Lab / Pharmacy web ]
            │                        │                            │
            └────────────────────────┼────────────────────────────┘
                                     │  HTTPS
                          ┌──────────▼──────────┐
                          │   Django backend     │
                          │   REST API + FHIR    │
                          │   Role-based access  │
                          └──────────┬──────────┘
                                     │
                     ┌───────────────┼────────────────┐
                     │               │                │
            ┌────────▼───────┐ ┌─────▼──────┐ ┌───────▼────────┐
            │  PostgreSQL     │ │ Access logs│ │ FHIR adapters  │
            │  (encrypted)    │ │ + backups  │ │ OpenMRS, DHIS2,│
            └────────────────┘ └────────────┘ │ lab, pharmacy  │
                                              └────────────────┘
```

## Backend

- **Python 3.12, Django 5** with Django REST Framework.
- One Django app per domain: `patients`, `referrals`, `consultations`, `laboratory`, `pharmacy`, `followup`, `reporting`.
- Role-based access with Django groups and object-level permissions. A professional only reaches records inside their own authorised care responsibility.
- Every read and write of patient data goes to an append-only access log.

## Database

- **PostgreSQL 16**, encryption at rest, TLS in transit.
- Unique patient identifier independent of phone number (shared phones are common). Phone is an attribute, never the key.
- Daily backups with tested restore procedure before pilot.

## Interoperability (HL7 FHIR)

- FHIR R4 resources: Patient, Encounter, ServiceRequest, Observation, MedicationRequest, MedicationDispense, Task.
- First connection: check what pilot partners actually run (OpenMRS, DHIS2, lab or pharmacy system), build and test **one** connection before expanding.
- Required for every connection: patient matching, consistent data definitions, source tracking, handling of failed and duplicate transfers.

## Low connectivity and offline

- Community worker app keeps a local queue of registrations and visits.
- Visible sync status on every screen ("last synced 14 min ago").
- Server-side deduplication by patient identifier plus timestamp so a retried upload never creates a duplicate record.

## Notifications

- SMS and in-app reminders carry no medical detail ("You have an appointment tomorrow at 11:00") so a shared phone does not expose a diagnosis.

## Reporting

- Aggregate reports for authorised teams only. Every report shows its coverage (which facilities) and last update time.
- Suspected and confirmed cases shown separately. Incomplete facility data is never presented as a population-wide rate.
- Outbreak alerts require agreed clinical definitions and authorised partners before activation. A potential signal is reviewed by a responsible professional before it is treated as an alert.

## Security checklist before pilot

- [ ] Individual accounts, no shared logins
- [ ] Role-based access tested per role
- [ ] Encryption at rest and in transit
- [ ] Access logs reviewed
- [ ] Backup and restore tested
- [ ] Secrets in environment variables, never in the repository
- [ ] Security review by an external party
