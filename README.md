# omnione-site — one static site, many pages (partner/outreach bundle)

**What this is:** the whole partner-outreach package as ONE deployable static site — the collaboration hub as the landing page, every demo + doc as a clean subpath off one domain. One upload = every link lives on a single domain; no more piling up separate Netlify sites.

**Host-agnostic:** every page is `<subpath>/index.html`, so the paths work under any host — a domain root (`yourdomain.com/act/`), a subdirectory (`yourdomain.com/site/act/`), or GitHub Pages. All internal links are relative. No build step, no framework, no external CSS/JS — pure static files.

## Structure
```
omnione-site/
  index.html            → the hub / landing (collaboration switchboard)
  cayce/index.html      → The 2027 vision comparison (was: incandescent-horse netlify)
  act/index.html        → ACT Resolution demo (value-based decision resolution wheel)
  os-readiness/index.html → OS-Readiness assessment (calculator demo)
  brief/index.html      → Collaborator brief
  pathway/index.html    → Partner alignment & ecosystem pathway
  survey/index.html     → Partnership alignment survey
  gateway/index.html    → Resource-share & licensing gateway
  ai-onboard/index.html → AI-to-AI onboarding prompt (paste-to-AI)
```

## Sources (for regeneration)
- Hub: `../omnione-collaboration-hub.html` (links re-pointed to local subpaths here)
- Cayce: `../cayce-2027-omnione-comparison.html`
- ACT: `../omni-obsidian-vault/projects/act-resolution/act-resolution-app.html`
- OS-Readiness: `../omni-obsidian-vault/projects/os-compare/assessment-demo.html`
- Docs (rendered md→html): `../omnione-for-collaborators.md` · `../partner-alignment-pathway.md` · `../partnership-alignment-survey.md` · `../resource-share-gateway.md` · `../omnione-ai-onboarding-prompt.md`

## Links still pointing off-site (deliberate — not part of this bundle)
- Alignment widget → `fastidious-moxie-355ec2.netlify.app` (separate demo, still live)
- New GDP video (YouTube) · New GDP overview (Notion)
- `ai-onboard/` still carries placeholder URLs (`[ACT app URL]`, `[CTC profile link]`) + external demo links — fill those with the deployed single-domain paths once the host is chosen.

## ⚠️ GUARDRAIL — do NOT tell Josh to delete `charming-gaufre-efc57e.netlify.app` yet
The hub's "2027 vision" link now points to the local `cayce/` page, **but this bundle is not deployed yet.** The old Netlify copies (`charming-gaufre`, and the demo sites) stay live until the bundle is published at its permanent home and the links verified there. Only then are the old per-demo sites deletable.

## Deploy — GitHub Pages via web upload (chosen 2026-07-26)

1. **Create the repo.** Go to https://github.com/new · Owner: **greenearthvision** · Name: **omnione-site** · **Public** (free GitHub Pages needs public) · do NOT add a README/gitignore (this folder has its own) · **Create repository**.
2. **Upload the files.** On the empty repo page click **"uploading an existing file"** (or **Add file → Upload files**). Open Finder at `omnione-site/`, select **everything INSIDE the folder** — `index.html`, all subfolders (`act`, `cayce`, `os-readiness`, `brief`, `pathway`, `survey`, `gateway`, `ai-onboard`), `README.md` — and drag them into the browser. **Drag the CONTENTS, not the `omnione-site` folder itself**, so `index.html` sits at the repo root. *(Optional: to include the hidden `.nojekyll`, press `Cmd+Shift+.` in Finder to show hidden files first — not critical here since no folders start with `_`.)* Commit message: "Add OmniOne partner site" → **Commit changes**.
3. **Turn on Pages.** Repo → **Settings** → **Pages** → Source: **Deploy from a branch** → Branch: **main**, folder: **/ (root)** → **Save**. Wait 1–2 min.
4. **Live at:** `https://greenearthvision.github.io/omnione-site/` (the Pages settings panel shows the exact URL once built). Click through `act/`, `cayce/`, `os-readiness/`, and the docs to verify.

**After it's live (hand the URL to Raven):** update `external-links.md` + the Notion links mirror with the single-domain URLs, fill the `ai-onboard` placeholders, and only THEN retire the old per-demo Netlify sites (guardrail lifts once verified live).

*Custom domain later (optional): Settings → Pages → Custom domain — point a subdomain (e.g. `explore.omnione.world`) at it.*
