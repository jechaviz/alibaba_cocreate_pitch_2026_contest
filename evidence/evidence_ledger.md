# Evidence Ledger

## Public Evidence

| Evidence | Path | Status |
|---|---|---|
| Opportunity research | `docs/research/ai_commerce_pitch_research_pack.md` | active |
| Current opportunity summary | `docs/research/current_opportunity.md` | active |
| Submission requirements | `docs/submission/requirements.md` | active |
| Product pitch | `docs/pitch/product_pitch.md` | active |
| Unit economics | `docs/pitch/unit_economics.md` | active |
| Demo MVP | `C:\git\websites\alibaba_cocreate_pitch_2026` | done |
| Backend/CLI | `C:\git\v_projects\alibaba_cocreate_pitch_2026` | done |
| Web QA screenshots | `evidence/web_qa/` | done |
| Automation plan | `automation/`, `runbooks/automation.md` | active |
| Submission packet | `submission/SUBMISSION_PACKET.md` | active |
| Filled product payload | `submission/accio_cocreate_payload.json` | active |

## Generated Evidence Targets

| Artifact | Command / Source | Output |
|---|---|---|
| ContestOps manifest | `v run C:\git\v_projects\contestops_ai -- manifest --profile alibaba` | `submission/generated/alibaba_manifest.json` |
| Checklist | `v run C:\git\v_projects\contestops_ai -- checklist --profile alibaba` | `submission/generated/alibaba_RULES_CHECKLIST.generated.md` |
| Evidence manifest | `v run C:\git\v_projects\contestops_ai -- evidence --profile alibaba` | `submission/generated/alibaba_EVIDENCE.generated.md` |
| Application packet | `v run C:\git\v_projects\contestops_ai -- application-packet --profile alibaba` | `submission/generated/alibaba_APPLICATION_PACKET.generated.md` |
| Unit economics JSON | product CLI | `evidence/unit_economics.json` |
| Demo manifest | product/web integration | `submission/demo_manifest.json` |
| Automation dry run | WAIBA dry-run playbook | `automation/evidence/dry-run/cocreate_submission_dry_run_trace.jsonl` |
