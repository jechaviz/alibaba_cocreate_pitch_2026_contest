# Alibaba CoCreate Pitch 2026 / Accio Work

Tag: `worth_it`

Track: `ai_startup_pitch`

Submission repo: `https://github.com/jechaviz/alibaba_cocreate_pitch_2026_contest`

Links:

- https://about.alibaba.com/cocreatepitch
- https://www.accio.com/work/cocreate_pitch

## Fechas

- Convocatoria 2026 abierta.
- Final Los Angeles: septiembre 2026.
- Final London: noviembre 2026.
- Revalidar deadlines exactos dentro de Accio Work/CoCreate form.

## Beneficio

- USD 1M+ prize pool segun anuncio 2026.

## Requisitos

- Pitch de producto/negocio.
- Uso de Accio Work / CoCreate Pitch flow.
- Tracks para founders, SMEs y estudiantes.

## Por que vale

Premia velocidad de negocio y producto, no necesariamente investigacion dura.
Es ideal para construir algo en dias: producto fisico+software, marketplace,
automation para comercio, sourcing, compliance o small business ops.

## Producto recomendado

`Accio Commerce Copilot`: AI commerce cockpit para pequenos importadores. Compara
proveedores, calcula landed cost, riesgos, compliance, payback y plan de
compra/venta.

## Arquitectura local

- Subrepo de oportunidad: `C:\git\v_projects\contests\worth_it\alibaba_cocreate_pitch_2026`
- Backend/CLI V: `C:\git\v_projects\alibaba_cocreate_pitch_2026`
- Web demo Vue3 CDN + UnoCSS: `C:\git\websites\alibaba_cocreate_pitch_2026`
- Reusable package generator: `C:\git\v_projects\contestops_ai`
- Automation/runbooks: `automation\`, `runbooks\`

## Artefactos

- Pitch: `docs\pitch\product_pitch.md`
- Unit economics: `docs\pitch\unit_economics.md`
- Video outline: `docs\media\video_outline.md`
- Checklist: `submission\checklist.md`
- Submission packet: `submission\SUBMISSION_PACKET.md`
- Research: `docs\research\ai_commerce_pitch_research_pack.md`
- Form map: `docs\submission\requirements.md`

## Sprint de 4 dias

1. Dia 1: idea y customer persona.
2. Dia 2: demo agentica con 3 flujos de sourcing.
3. Dia 3: unit economics y supplier/risk dashboard.
4. Dia 4: video corto + pitch + Accio Work submission.

## Regenerar paquete ContestOps

```powershell
v run C:\git\v_projects\contestops_ai -- manifest --profile alibaba submission\generated\alibaba_manifest.json
v run C:\git\v_projects\contestops_ai -- checklist --profile alibaba submission\generated\alibaba_RULES_CHECKLIST.generated.md
v run C:\git\v_projects\contestops_ai -- evidence --profile alibaba submission\generated\alibaba_EVIDENCE.generated.md
v run C:\git\v_projects\contestops_ai -- application-packet --profile alibaba submission\generated\alibaba_APPLICATION_PACKET.generated.md
```
