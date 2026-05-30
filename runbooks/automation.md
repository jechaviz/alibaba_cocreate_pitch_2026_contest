# Submission Automation Runbook

Scope: Alibaba CoCreate Pitch 2026, track `ai_startup_pitch`, with Accio Work as the likely account/application surface.

Public surfaces rechecked on 2026-05-29:

- `https://about.alibaba.com/cocreatepitch`
- `https://www.accio.com/work/cocreate_pitch?src=p_eventpitch_ytkol_jonlawweb`
- `https://www.accio.com/work/cocreate_pitch/student_track?src=p_eventpitch_ytkol_jonlawweb`

The public pages confirm the competition/application surfaces, but the full form appears to be account-gated or app-routed. Treat the field inventory as a draft until an authorized operator session confirms exact labels, required markers, upload constraints, and deadlines.

## Files

- `automation/form_payload.template.json`: reusable placeholder-only payload template. Do not put credentials, MFA codes, cookies, session tokens, or private secrets here.
- `automation/form_inventory.yml`: expected field inventory, evidence folder conventions, dry-run controls, and explicit handoff gates.
- `automation/waiba/cocreate_submission_dry_run.playbook.yml`: safe local dry run. It creates evidence folders and traces scaffold checks without opening external pages.
- `automation/waiba/cocreate_live_prep.playbook.yml`: visible-browser preparation for an operator-led authorized session. It opens public/application surfaces and records handoff gates.
- `automation/vimport_env_profile.refs.env`: VImport vault-ref profile for local session credentials or tokens if an authorized flow later needs them.
- `automation/account_creation_policy.yml`: public, redacted policy for using the profile primary Gmail in authorized Accio/Alibaba account creation.
- `automation/waiba/default_edge_account_session.playbook.yml`: opens official surfaces in the existing Microsoft Edge profile instead of WAIBAv's isolated browser profile.
- `submission/profile_resolution_redacted.md`: public receipt of applicant fields resolved from the local profile without publishing private values.
- `submission/private/accio_cocreate_payload.private.json`: ignored local payload with applicant fields filled from `C:\git\customers\yo\profile\jecha_profile.yml`.
- `submission/private/account_registry.private.yml`: ignored local registry for account slots, reserved passwords, and vault refs.

## Applicant Profile Resolution

The local profile was used to resolve applicant identity, contact, location,
role, public professional links, and candidate legal-entity context. Private
identity, fiscal, signature, account, and document-inventory data remain out of
public artifacts.

Use the private payload only in an authorized operator session:

```powershell
$root = "C:\git\v_projects\contests\worth_it\alibaba_cocreate_pitch_2026"
Get-Content "$root\submission\private\accio_cocreate_payload.private.json" | ConvertFrom-Json | Out-Null
```

VImport vault refs are available for future authorized session material:

```powershell
cd C:\git\v_projects\vimport
v run . -- vault-init alibaba_cocreate_pitch_2026
Get-Content "$root\automation\vimport_env_profile.refs.env"
```

## Authorized Edge Account Session

Use this when the goal is to connect or create the Accio Work / Alibaba account
through the existing Microsoft Edge profile:

```powershell
$root = "C:\git\v_projects\contests\worth_it\alibaba_cocreate_pitch_2026"
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 validate "$root\automation\waiba\default_edge_account_session.playbook.yml" prod
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 run "$root\automation\waiba\default_edge_account_session.playbook.yml" prod
```

This flow may create/connect accounts only with the profile primary Gmail.
CAPTCHA, MFA, terms, eligibility, and final submit remain operator gates.

## Dry Run

Default behavior is dry-run only. Use it before any live form session:

```powershell
$root = "C:\git\v_projects\contests\worth_it\alibaba_cocreate_pitch_2026"
Get-Content "$root\automation\form_payload.template.json" | ConvertFrom-Json | Out-Null
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 validate "$root\automation\waiba\cocreate_submission_dry_run.playbook.yml" prod
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 run "$root\automation\waiba\cocreate_submission_dry_run.playbook.yml" prod
```

Expected dry-run output:

- `automation/evidence/dry-run/`
- `automation/evidence/dry-run/screenshots/`
- `automation/evidence/dry-run/receipts/`
- `automation/evidence/dry-run/operator-notes/`
- `automation/evidence/dry-run/cocreate_submission_dry_run_trace.jsonl`

## Live Prep

Use live prep only with an authorized operator present:

```powershell
$env:CONTESTOPS_DRY_RUN_MODE = "true"
$env:CONTESTOPS_ALLOW_DRAFT_FILL = "false"
$env:CONTESTOPS_ALLOW_FINAL_SUBMIT = "false"
$root = "C:\git\v_projects\contests\worth_it\alibaba_cocreate_pitch_2026"
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 validate "$root\automation\waiba\cocreate_live_prep.playbook.yml" prod
powershell -NoProfile -ExecutionPolicy Bypass -File C:\Users\jecha\.codex\skills\waiba\scripts\invoke-waiba.ps1 run "$root\automation\waiba\cocreate_live_prep.playbook.yml" prod
```

Live prep opens:

- CoCreate public page for current program copy, deadlines, and routing.
- Accio Work CoCreate page for application entry.

Live prep does not fill or submit by default. Keep `CONTESTOPS_ALLOW_DRAFT_FILL=false` until exact selectors and field limits have been captured and reviewed.

## Operator Handoffs

The operator, not automation, must complete these steps:

- Accio Work, Alibaba.com, CoCreate, email, phone, or social login.
- CAPTCHA, slider, bot checks, device trust, and MFA.
- Reading and accepting rules, eligibility, terms, privacy, marketing, and SMS language.
- Native OS file picker uploads unless the operator approves exact paths.
- Final submission.

Automation may record that a handoff happened, capture redacted screenshots after approval, and resume only after the operator says the session is ready.

## Evidence

Use timestamped folders for every session:

- `automation/evidence/YYYYMMDD-HHMMSS-cocreate-dry-run/`
- `automation/evidence/YYYYMMDD-HHMMSS-cocreate-live-prep/`

Use these subfolders:

- `screenshots`: redacted browser screenshots.
- `html`: sanitized HTML snapshots only after operator approval.
- `network`: redacted request metadata only; no auth headers, cookies, or tokens.
- `receipts`: saved draft receipts, confirmation pages, and official emails.
- `exports`: reviewed payload copies and field maps.
- `operator-notes`: notes for auth, CAPTCHA, upload, and submit handoffs.

Redact verification codes, cookies, authorization headers, private financials, non-public phone numbers, and any material not intended for the final application.

## Field Discovery

During the first authorized session:

1. Open `automation/form_inventory.yml` beside the live form.
2. Record exact visible labels, required markers, character limits, file type limits, and order of fields.
3. Mark each inventory row as `verified`, `renamed`, `removed`, or `new_live_field`.
4. Add stable selector hints only after confirming they survive reload.
5. Save draft, capture receipt, and stop for operator review.

Do not click final submit during discovery.

## Final Submit Gate

Final submission requires all of the following:

- Final payload values reviewed against the deck, demo, video, and evidence.
- Private applicant payload reviewed against the official form labels.
- Required uploads manually confirmed in the form.
- Terms, rules, eligibility, privacy, and marketing choices manually reviewed.
- Saved-draft or preview screenshot captured.
- `CONTESTOPS_ALLOW_FINAL_SUBMIT=true`.
- Operator gives explicit in-session confirmation.

Even with the environment flag set, automation must pause at the submit button if the visible page text or target track differs from `ai_startup_pitch`.
