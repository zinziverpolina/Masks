---
name: website-manager
description: Manager knowledge for Polina Zinziver's websites — the commercial and artistic portfolio (zinziverpolina/portfolio on GitHub Pages), the CV, the ZINZIVER logo, and every Claude chat working on them. Use whenever a task touches the site, its pages, layout, media weight, 3D models, logo, or when coordinating/reviewing work done by several chats on the site — even if the user just says "сайт", "портфолио", "страница проекта", "вес сайта", "логотип на сайт" or names a project page (LOEWE, Nina Ricci, Sacred Hyper Race…).
---

# Website manager — Polina Zinziver

Distilled from the «веб-сайт-менеджер» chat (5–7 Oct 2026), which read the chats «LOGO ZINZIVER» and
«Модели для веб-карточек» and the site repo. Polina asked that this knowledge go to the LOGO ZINZIVER chat.
Works together with the skills `artist-portfolio` (her rules for texts/CV/sites), `web-model-cards`
(GLB pipeline), `comfyui-studio` and `picks-driven-generation` (logo generation), `zinziver-dossier`.

## Where things live

| What | Where |
|---|---|
| Site repo | `zinziverpolina/portfolio`, branch `main`, GitHub Pages → https://zinziverpolina.github.io/portfolio/ |
| Commercial home | `commercial.html` — floating 3D intro (`commercial/float-scene.js`, three.js 0.169 + cannon-es), cycling logo `commercial/img/logo/zz-XX.webp`, "ALL PROJECTS" menu |
| Project pages | `commercial/<slug>.html`; LOEWE is one page `commercial/loewe.html` (SS22 · Christmas · Perfumes); old `loewe-ss22.html`/`loewe-christmas.html` redirect |
| Artistic site | `index.html` (same repo) |
| Shared | `style.css`, `site.js`, `zoom.js` (CSS zoom from a 1470 px MacBook Air layout), `picker.js` (`?pick` tick-to-keep mode), `?edit` editor + `layout.json` |
| Black pages | HYPERTRASH, CAROLINA SARRIA, Posters — `commercial/collage.js` paper-collage stage |
| Sky scenes | `sky/` (chrome name, LOEWE Live Laugh Loewe words in an HDRI sky) |
| Hidden pages | `commercial/drafts.html`, `dub.html`, `review/nothing/` (Nothing AD review), `commercial/loewe-test.html` (scatter test) |
| CV | `zinziverpolina/Polina-CV` → https://zinziverpolina.github.io/Polina-CV/ |
| Polina's local clone | `C:\Users\Asus\portfolio-site` (Windows PC, RTX 3080 laptop) |
| Manager notes | repo `zinziverpolina/Masks`, branch `claude/sleepy-cray-04ybi6`, folder `website-manager/` (STATUS.md, videos CSV, this skill) |

Palette now: navy `#2a27a6` (hover, titles), sky `#5d8ab6` (frames, subtitles). Frames = 1 px line + 8 small
white squares + number + caption on hover (`.shr-frame`). Type evolved: caps sans 500 for headers; Times/Tinos
italic meta; titles and CV/INSTAGRAM moved to Bricolage Grotesque (8 Oct). Check the live CSS before assuming.

## How Polina works (rules learned)

- Answer in Russian; site texts in English. Never invent years, roles, clients, credits — ask.
- **Show before publishing.** Build locally / as an unlisted test copy, give her the link, push to the real page
  only after her OK. (The manager once pushed a test page to `main` without asking — she should be told first.)
- She works by voice and decides fast: "оставляем", "убери нахер", exact numbers. Apply literally, then show.
- She selects by ticking: drafts open in `picker.js`; "what is ticked stays". Logo picks go through gallery
  artifacts with a db of picks.
- Never buy anything, never download paid assets without asking. Third-party models in her folders must be
  flagged, not silently used.
- Big decisions stay hers: project order, what is commercial vs artistic, which media stay.
- Put heavy, final-stage work (compression, Vimeo swaps) **last** — her decision of 5 Oct.

## Coordinating chats

Several chats push to the same `main` at once (one deleted frames another was using as logo references).
- Give each chat its own zone (files/pages); announce before touching another chat's page.
- Always `git fetch` + rebase before pushing; small commits with clear messages.
- Experiments go to separate files (`*-test.html`, separate CSS/JS) so live pages stay intact.
- Chats on her PC are reachable only while the PC is on and the app open (Remote Control).
- Read `references/chats.md` for the roster and what each chat owns.

## References

- `references/status.md` — open tasks for the site and the logo (as of 7–8 Oct).
- `references/weight.md` — measured site weight, heaviest videos/pages, compression tests, 3D optimisation plan.
- `references/scatter.md` — the framed drag-and-drop layout built for LOEWE (scatter.js) and its open choices.
- `references/chats.md` — chats, their zones and history.
- `references/logo.md` — ZINZIVER logo decisions, finalists, licences.
