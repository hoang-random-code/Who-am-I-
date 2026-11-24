# 07: Security review: scroll-craft (third-party skill)
Reviewed: 2026-11-24 · Upstream https://github.com/nateherkai/scroll-craft (MIT) · Commit 75d81f74e83692add18cd7a8a8e078b8a887a579 (v0.3.1)
Clone location: `~/vendor/scroll-craft` (outside the repo, not committed)

## Verdict: Low risk if `kie.mjs` is not used. Medium if it is.

| File | Executes? | Network | Secrets / FS | Finding |
|---|---|---|---|---|
| engine/scrollcraft.js (62 KB) | In the visitor's browser | `fetch(src)` of the page's own video assets only | none | No wheel/touch `preventDefault`, so native scroll is kept. Honours `prefers-reduced-motion` (clips not fetched, no smoothing). No external hosts. |
| engine/scrollcraft.css | n/a | `http://www.w3.org` = SVG namespace string, not a request | none | OK |
| scripts/kie.mjs | Node | **api.kie.ai** + **kieai.redpandaai.co** (third-party upload host) | Reads `KIE_AI_API_KEY` from env, or walks up to 8 parent dirs for a `.env` (reads only that line) | Sends the API key as Bearer to *both* hosts. `--ref` uploads local images base64 to the upload host. **Do not run without explicit yes.** Hosts are not in the network allowlist anyway. |
| scripts/doctor.mjs | Node | none (optional `--probe` calls kie.mjs) | Checks for the key's *presence*, runs local `node/ffmpeg/chrome` version checks | OK. Never pass `--probe`. |
| scripts/serve.mjs | Node | Binds 127.0.0.1 by default; `--lan` = 0.0.0.0 | Serves files under `--root` | OK. Never use `--lan`. |
| scripts/shoot.mjs, worldflight-assert.mjs | Node + headless Chrome | localhost only | Writes screenshots/report.json to an output dir; spawns ffmpeg | Pattern-scanned, not read line by line |
| scripts/encode.sh | bash | none | Finds a local ffmpeg build | OK |
| scripts/workspace.mjs | Node | none | Creates workspace dirs under `SCROLLCRAFT_HOME` | OK |
| SKILL.md, references/*.md | Instructions (treated as data) | n/a | n/a | No instructions to exfiltrate, add telemetry or change permissions found by keyword scan; full read happens at build time |

## Not checked
- Line-by-line read of shoot.mjs (33 KB), worldflight-assert.mjs and all reference markdown (keyword and pattern scan only).
- npm dependency `playwright-core` (the build step installs it; pin the version at install time).
- The three .webp files in /media (images, not executed).
