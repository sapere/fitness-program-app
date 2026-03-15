# TRAIN — 3× Indoor Programme

A personal fitness web app for a structured 3-times-per-week indoor training programme. Built as a single HTML file, hosted on GitHub Pages with Supabase for cross-device sync.

**Live app → [sapere.github.io/fitness-program-app](https://sapere.github.io/fitness-program-app)**

---

## About the programme

The structure is based on well-evidenced training principles:

- **Full-body, 3× per week** — each muscle group trained 3 times weekly, which meta-analyses show produces equal or superior hypertrophy compared to body-part splits (Schoenfeld et al., 2016)
- **Progressive overload** — sets, reps, load and cardio intensity increase across the 6-week build
- **Rep range 8–15** — effective for hypertrophy and joint-friendly for the 45–55 age group
- **Deload every 6 weeks** — reduces accumulated fatigue, restores hormonal balance, protects joints and CNS. You lose no muscle during a properly structured deload

**Protein target:** 1.6–2.0 g/kg bodyweight per day — the single most important nutritional lever for body recomposition.

---

## Multi-user support

Each person gets their own synced data by adding `?user=yourname` to the URL:

```
https://sapere.github.io/fitness-program-app?user=sand
https://sapere.github.io/fitness-program-app?user=jane
```

- Progress, session history and weight logs are completely separate per user
- Data syncs across all devices in real time via Supabase
- If offline, data is saved locally and syncs when connection is restored
- Bookmark your personal URL to skip the name prompt

---

## How to use the app

### 1. Select your current week

Eight week buttons represent one full training cycle. Weeks 1–6 are the build phase; weeks 7–8 are the deload. Each week shows:

- Sets and reps to perform
- Target RPE (Rate of Perceived Exertion, 1–10 scale)
- Rest time between sets
- The cardio finisher protocol
- A load/volume intensity bar showing progression at a glance

### 2. Select your session (A, B, or C)

Rotate through sessions A → B → C across your three weekly training days. No fixed days — just do them in order with at least one rest day between. The app remembers your last session and shows a green dot on the next one to do.

| Day | Session |
|-----|---------|
| Monday | A |
| Wednesday | B |
| Friday | C |

### 3. Work through the session

Each session has three phases:

**Warm-up (5 min)** — dynamic movements to prepare joints and muscles. Do not skip.

**Resistance training (~28 min)** — 4 exercises per session. For each exercise:
- Tap circles to tick off completed sets (card turns green when all sets done)
- Tap **Rest Xs** after a set to start the countdown timer with audio beeps
- Log your weight and reps — the app tracks personal bests (🏆 PB badge)
- Tap **Watch demo on YouTube** for a form tutorial

**Cardio finisher (7 min)** — tap **Start finisher timer** to auto-count rounds. The timer alternates between WORK (green) and REST (blue) phases with audio cues. Work/rest ratio gets harder each week.

### 4. Mark the session complete

Tap **Mark session complete** at the bottom. This syncs to Supabase and updates your progress across all devices. You get confetti. 🎉

### 5. Track progress

Tap **Progress** in the top-right:
- Total sessions completed
- Current training day streak (🔥 shown in header)
- Full session history with dates

---

## Sessions explained

### Session A — Lower body + Push

Front of lower body (quads, glutes) combined with upper body pushing movements.

| Exercise | Primary muscles |
|----------|----------------|
| Goblet squat | Quads, glutes, core |
| Dumbbell bench press | Pectorals, triceps, anterior delts |
| Bent-over row | Lats, mid-back, biceps |
| Plank + shoulder taps | Core anti-rotation, shoulder stability |

> The row is included to balance the push and keep shoulder health in check.

---

### Session B — Hinge + Pull

Posterior chain (hamstrings, glutes, lower back) combined with pulling movements. Most demanding on the back and legs.

| Exercise | Primary muscles |
|----------|----------------|
| Romanian deadlift (DB) | Hamstrings, glutes, lower back |
| Overhead press (DB) | Shoulders, triceps, upper back |
| Lat pulldown / cable row | Lats, rhomboids, biceps |
| Dead bug | Deep core, anti-extension |

> Schedule basketball away from Session B — hamstrings and lower back need recovery time.

---

### Session C — Compound+ (weak links)

Different angles from A and B, with specific focus on rear delts and rotator cuff — the most commonly neglected muscles and most important for shoulder health and posture.

| Exercise | Primary muscles |
|----------|----------------|
| Reverse lunge (DB) | Quads, glutes, single-leg balance |
| Incline DB press | Upper pectorals, anterior delts |
| Rear delt fly / face pull | Rear delts, external rotators, rhomboids |
| Pallof press / side plank | Obliques, core anti-rotation |

> The rear delt fly and Pallof press are the two people skip most. Don't — they prevent shoulder and lower back injuries.

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

After week 8, restart at week 1 with slightly heavier weights than the previous cycle.

---

## Features

- Cross-device sync via Supabase (sessions + weight logs)
- Offline fallback to localStorage when no connection
- Multi-user support via `?user=name` URL parameter
- Rest timer with audio countdown, ring animation, and beep on completion
- Finisher interval timer — auto-counts rounds, alternates WORK/REST with audio
- Per-set tick tracker on every exercise
- Weight logging per exercise with personal best detection
- Last session memory — always shows which session to do next
- Day streak counter with 🔥 badge
- Confetti on session completion
- YouTube demo link for every exercise
- Print / PDF export (File → Print → Save as PDF)
- Mobile friendly

---

## Tech stack

Single `index.html` file. No frameworks, no build step. Google Fonts for typography, Supabase JS SDK (via CDN) for database sync. Falls back to `localStorage` when offline.

**Backend:** Supabase (PostgreSQL) — two tables: `sessions` and `weights`, both with Row Level Security enabled.

---

## Updating the app

```bash
cp ~/Downloads/index.html /path/to/fitness-program-app/
cd /path/to/fitness-program-app
git add index.html
git commit -m "fix: describe what changed"
git push
```

GitHub Pages redeploys automatically within ~30 seconds.

---

## Security notes

The Supabase anon key in the HTML source is intentional and safe — it is a public key by design. Data is protected by Row Level Security policies on the database. Without proper authentication (email/password login), data is scoped by username tag only — suitable for a private app shared between trusted people, not a public-facing product.

---

## License

MIT — do whatever you want with it.
