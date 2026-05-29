# Applicant Profile Resolution

Source profile: `C:\git\customers\yo\profile\jecha_profile.yml`

This file records what was resolved for the Accio Work / CoCreate Pitch form
without publishing private applicant values.

## Resolved Into Private Payload

- Legal applicant name: resolved from local profile.
- Preferred/public applicant name: resolved from local profile.
- Email and phone: resolved from local profile and stored only in ignored private payload.
- Country and city/state: resolved from local profile.
- LinkedIn and GitHub profile URLs: resolved from local profile.
- Role title: resolved from current professional profile.
- Founder/operator summary: derived from professional profile without exposing private IDs.
- Candidate legal entity: resolved from current professional profile and marked for operator review.

Private output:

- `submission/private/accio_cocreate_payload.private.json`

## Explicitly Excluded From Public Artifacts

- RFC, CURP, birth date, fiscal profile, CSD certificate/key references.
- Signature images and identity document inventories.
- OneDrive document manifests and OCR text from personal documents.
- Account login metadata, MFA, cookies, tokens, and session material.
- Any final terms, privacy, or eligibility acceptance.

## Reusable Tooling Used

- `vimport` generated vault-ref env profile and initialized local vault:
  `VAULT:alibaba_cocreate_pitch_2026:<SECRET_NAME>`.
- `veloclaw` ran VImport activation readiness against `C:\git\v_projects`.
- `waibav` planned the live-prep playbook and classified the run as medium risk
  because it opens browser surfaces but does not submit.

## Remaining Operator Review

- Confirm exact legal/entity field requested by the official form.
- Confirm whether the form wants individual applicant, company, or team name.
- Confirm country/region format if the UI uses dropdown values.
- Confirm final terms, privacy, eligibility, marketing, and submit choices inside
  the authorized Accio Work session.
