# The SafiriCare care journey

The first working care journey the platform demonstrates:

Registration → Referral → Facility response → Consultation / testing → Prescription → Pharmacy collection → Follow-up

Every step records three things: **status**, **responsible person**, and **next action**.

## The 7 steps (as shown in the prototype)

| # | Step | Responsible role | What is recorded | Next action |
|---|---|---|---|---|
| 1 | Registration | Community worker | Patient identity, concern, consent, care record opened | Create referral |
| 2 | Referral | Community worker → Clinic | Referral sent to nearest equipped facility | Facility responds |
| 3 | Facility response | Clinic / hospital | Accept or redirect, appointment time, estimated wait | Consultation |
| 4 | Consultation / testing | Clinic / hospital, Laboratory | Consultation notes, test request, verified results linked to the correct patient and request | Prescription or follow-up |
| 5 | Prescription | Clinic / hospital | Authorised prescription sent digitally to pharmacy | Pharmacy verification |
| 6 | Pharmacy collection | Pharmacy | Prescription verified, availability confirmed, full or partial dispensing, supplying pharmacy | Follow-up scheduled |
| 7 | Follow-up | Community worker | Visit completed, patient status, next check date | Close or continue |

## Important rules (from the development brief)

- Medication collection does **not** mean the patient took the medicine or recovered. Follow-up is a separate step.
- Suspected infection, test result, clinician-confirmed diagnosis, treatment and follow-up are tracked **separately**.
- Notifications to patients never contain sensitive medical details.
- Each professional sees only the steps that fall under their authorised care responsibility.
- Patients without smartphones are supported through the community worker, who sees the same journey on their behalf.

## Demo patient

The prototype uses one fictional patient, "Amina K.", 28, week 32 of pregnancy, Kinshasa district, with a suspected pre-eclampsia pathway. All names, values and times are invented for demonstration.
