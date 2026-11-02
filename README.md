---
project: Orchestrator Academy
type: single-file web app
status: live (v1.3)
stack: HTML + vanilla JS + localStorage (zero deps, offline)
origin: Outskill "AI Orchestration" live workshop transcript
entry: index.html (double-click to run)
---

# Orchestrator Academy

Gamified learning webapp that turns every lesson, prompt and framework from the live
AI Orchestration workshop into clickable missions. Learn the orchestrator skill by playing it:
read → quiz → earn XP → unlock tracks → pass the final exam → forge your certificate.

## How to run
Double-click `index.html`. No server, no install, no internet needed.
Works in any modern browser. Progress auto-saves to localStorage.

## Feature set
- **29 lessons** across 6 tracks (Bonus warm-up + Levels 1–5), each with read blocks,
  pro-tips, workshop stories and a ready-to-copy prompt
- **Per-lesson quizzes** (+10 XP per correct answer, best score banked, review mode prevents re-farming)
- **Track gating** — finish ~3 lessons of a track to unlock the next
- **7 ranks** (Novice → Legendary Orchestrator) + **10 badges** (incl. Perfect Run, Agent Overlord)
- **Final exam** (10 Qs, 7+ to pass) locked until Level 5's last mission → **+250 XP** + printable certificate (name input, print-to-PDF)
- **Daily streak** with flame pulse animation
- **Backup / Restore** — one-click JSON progress export + validated import (XP clamped to legal max, badges re-granted)
- **Daily study reminder** — welcome-back CTA toast (opens your next mission directly) + idle nudges while tab is open
- **SVG icon system** — every icon is inline SVG (57-entry library), no emoji, no CDN
- **Animations** — staggered cards, XP pop/float, rank-up toast, progress-bar shine, reduced-motion guard

## Data & storage
| Key | Value |
|-----|-------|
| localStorage key | `orchestratorAcademy_v1` |
| State schema | `{ xp, done[], bestQuiz{}, examScore, examPassed, lastVisit, streak, badges[], name, remLast }` |
| XP economy | lessons 30–40 XP base + quiz bonus, exam +250, max total 2,250 |

## File map
Single file — everything (CSS, data, logic) lives in `index.html`:
- `ICE` icon library + `ic()` builder + `emojicon()` (toast emoji→SVG)
- `TRACKS[] / EXAM[] / BADGES[] / RANKS` — all content is data-driven
- `exportProgress() / importProgress() / dailyReminder() / initIdleNudge() / floatXp()`

## Changelog
- **v1.0 (Oct 31)** — full app from workshop transcript; 29 lessons, exam, certificate, badges
- **v1.1 (Oct 31)** — emoji → dedicated inline SVG icons everywhere
- **v1.3 (Nov 1)** — JSON backup/restore, daily study reminder + idle nudges, animation system

## Credits
Built from the flagship **AI Orchestration** live course by **Outskill** (https://outskill.com)
— every lesson, prompt and framework comes from that workshop, distilled into this
gamified, fully offline study companion.
