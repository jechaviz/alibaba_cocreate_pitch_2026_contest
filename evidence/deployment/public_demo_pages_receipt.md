# Public Demo Deployment Receipt

Generated: 2026-05-29

Public demo URL:

```text
https://jechaviz.github.io/alibaba_cocreate_pitch_2026_web/
```

GitHub repository:

```text
https://github.com/jechaviz/alibaba_cocreate_pitch_2026_web
```

GitHub Pages source:

```text
branch: main
path: /
status: built
```

HTTP verification:

```text
status: 200
title marker: Accio Work Commerce Demo
runtime marker: vue3-sfc-loader
```

WAIBAv verification:

```text
playbook: automation/waiba/public_demo_qa.playbook.yml
trace: automation/evidence/public-demo/public_demo_qa_trace.jsonl
result: public demo opened with Browser.Open after waibav Browser.Open support was added
```

Veloclaw snapshots:

```text
contest repo snapshot: d829151f591d0307
web repo snapshot: ed4c6b229d8d76c8
waibav repo snapshot: 9fdcfe9f2a3247fd
```

Profile/application evidence:

```text
vimport manifest: evidence/profile/jecha_redacted_profile_manifest.json
vimport application packet: evidence/profile/jecha_profile_application_packet.json
account/session policy: automation/account_creation_policy.yml
edge session trace: automation/evidence/default-edge-session/default_edge_account_session_trace.jsonl
```

Submission usage:

- Use the public demo URL for form fields that request a product website, demo,
  or prototype link.
- Keep the local URL only as fallback evidence for judge walkthroughs.
- Do not upload private profile payloads or session traces.
