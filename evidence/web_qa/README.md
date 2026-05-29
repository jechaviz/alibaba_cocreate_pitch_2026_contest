# Web QA Evidence

Demo URL: `http://127.0.0.1:8787/`

Web repo: `https://github.com/jechaviz/alibaba_cocreate_pitch_2026_web`

Captured on: 2026-05-29

## Checks

- HTTP status: `200`
- Vue mounted content includes `Accio Work commerce launch console`.
- Desktop screenshot: `desktop_1440x900.png`
- Mobile screenshot: `mobile_390x844.png`
- Competitive desktop screenshot: `desktop_competitive_1440x900.png`
- Competitive mobile screenshot: `mobile_competitive_390x844.png`
- Worker QA also verified product switch, price edit, Accio action progress, and no runtime exceptions through headless Chrome/CDP.
- Competitive QA verified `Competition-aware judge mode`, rival workflow tabs, score delta, and judge proof CTA in rendered DOM.

## Caveats

- CDN internet access is required for Vue 3, UnoCSS runtime, and `vue3-sfc-loader`.
- Demo interactions are simulated local state for the pitch MVP.
