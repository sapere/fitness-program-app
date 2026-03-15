# TRAIN — 3× Indoor Programme

A personal fitness web app for a structured 3-times-per-week indoor training programme. Built as a single HTML file, hosted on GitHub Pages — no server, no dependencies, works offline.

**Live app → [sapere.github.io/fitness-program-app](https://sapere.github.io/fitness-program-app)**

---

## About the programme

The structure is based on well-evidenced training principles:

- **Full-body, 3× per week** — each muscle group trained 3 times weekly, which meta-analyses show produces equal or superior hypertrophy compared to body-part splits (Schoenfeld et al., 2016)
- **Progressive overload** — sets, reps, load and cardio intensity increase across the 6-week build
- **Rep range 8–15** — effective for hypertrophy and joint-friendly for the 45–55 age group
- **Deload every 6 weeks** — reduces accumulated fatigue, restores hormonal balance, protects joints and CNS. You lose no muscle during a properly structured deload

**Current activity baseline:** 1 hour of basketball per week + occasional 5 km walks. The programme builds from this base.

**Protein target:** 135–168 g/day (1.6–2.0 g/kg bodyweight) — the single most important nutritional lever for body recomposition.

---

## How to use the app

### 1. Select your current week (top of the page)

Eight week buttons represent one full training cycle. Weeks 1–6 are the build phase; weeks 7–8 are the deload. Each week shows:

- How many sets and reps to do
- Your target RPE (Rate of Perceived Exertion, 1–10 scale)
- How long to rest between sets
- The cardio finisher protocol
- A load/volume intensity bar so you can see the progression at a glance

### 2. Select your session for today (A, B, or C)

Rotate through sessions A → B → C across your three weekly training days. There is no fixed day — just do them in order with at least one rest day between sessions. A typical week might be:

| Day | Session |
|-----|---------|
| Monday | A |
| Wednesday | B |
| Friday | C |

### 3. Work through the session

Each session has three phases:

**Warm-up (5 min)** — dynamic movements to prepare the joints and muscles. Do not skip this.

**Resistance training (~28 min)** — 4 exercises with sets, reps and RPE shown for the selected week. For each exercise:
- Tap the circles to tick off completed sets
- Tap **Rest Xs** after finishing a set to start the countdown timer
- The card highlights when all sets are done
- Tap **Watch demo on YouTube** for a form tutorial if you're unsure of the movement

**Cardio finisher (7 min)** — interval-based cardio at the end of the session. The work/rest ratio gets harder each week.

### 4. Mark the session complete

At the bottom of the page, tap **Mark session complete** when you finish. This saves the session to your browser's local storage and adds it to your progress log.

### 5. Track progress

Tap **Progress** in the top-right to see:
- Total sessions completed
- Current day streak
- Full session history with dates

---

## Sessions explained

### Session A — Lower body + Push

Focuses on the front of the lower body (quads, glutes) combined with pushing movements for the upper body (chest, shoulders, triceps).

| Exercise | Primary muscles |
|----------|----------------|
| Goblet squat | Quads, glutes, core |
| Dumbbell bench press | Pectorals, triceps, anterior delts |
| Bent-over row | Lats, mid-back, biceps |
| Plank + shoulder taps | Core anti-rotation, shoulder stability |

> The row is included here to balance the push movement and keep shoulder health in check.

---

### Session B — Hinge + Pull

Focuses on the posterior chain (hamstrings, glutes, lower back) combined with pulling movements. This is the most demanding session on the back and legs.

| Exercise | Primary muscles |
|----------|----------------|
| Romanian deadlift (DB) | Hamstrings, glutes, lower back |
| Overhead press (DB) | Shoulders, triceps, upper back |
| Lat pulldown / cable row | Lats, rhomboids, biceps |
| Dead bug | Deep core, anti-extension |

> Schedule basketball away from Session B — your hamstrings and lower back will need recovery time.

---

### Session C — Compound movements + Weak links

A varied session that hits different angles from A and B, and specifically targets rear delts and rotator cuff — the muscles most commonly neglected and most important for shoulder health and posture at 49.

| Exercise | Primary muscles |
|----------|----------------|
| Reverse lunge (DB) | Quads, glutes, single-leg balance |
| Incline DB press | Upper pectorals, anterior delts |
| Rear delt fly / face pull | Rear delts, external rotators, rhomboids |
| Pallof press / side plank | Obliques, core anti-rotation |

> The rear delt fly and Pallof press are the two exercises people are most tempted to skip. Don't — they directly prevent shoulder and lower back injuries.

---

## The 8-week cycle

| Week | Phase | Sets | Reps | Intensity |
|------|-------|------|------|-----------|
| 1 | Foundation | 2 | 12–15 | 30% — learn the movements |
| 2 | Volume+ | 3 | 12–15 | 42% — add the third set |
| 3 | Load+ | 3 | 10–12 | 55% — increase weight |
| 4 | Load+ | 3 | 10–12 | 67% — push to 1–2 reps from failure |
| 5 | Intensity | 3 | 8–10 | 80% — heavier, 0–1 RIR |
| 6 | Peak | 4 | 8–10 | 96% — maximum effort |
| 7 | Deload | 2 | 12–15 | 35% — 60–70% of week 6 load |
| 8 | Deload | 2 | 12–15 | 30% — mobility and technique only |

After week 8, start over at week 1 — but you should be able to use slightly heavier weights than the previous cycle.

---

## Features

- Rest timer with audio countdown and ring animation
- Per-set tick tracker on every exercise
- YouTube demo link for every exercise
- Progress log saved to browser local storage
- Print / PDF export (File → Print → Save as PDF)
- Fully offline — no server, no account, no tracking
- Mobile friendly

---

## Tech stack

Single `index.html` file. No frameworks, no build step, no dependencies beyond two Google Fonts. Data stored in browser `localStorage`.

---

## Updating the app

```bash
# Make changes to index.html, then:
cd /path/to/fitness-program-app
cp ~/Downloads/index.html .
git add index.html
git commit -m "fix: describe what changed"
git push
```

GitHub Pages redeploys automatically within ~30 seconds.

---

## License

MIT — do whatever you want with it.
