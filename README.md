# ProjectGenesis 

This is the sample **week-by-week execution plan**. May adjust as I go.
Format per week:
- **Goal** = what the week is for
- **Must Achieve** = minimum wins (proof-based)
- **Sample Focus (flexible)** = examples only (swap as needed)
- **If Lost** = the next 1–2 actions to restart momentum

---

## Rules (never change)
- **Max 3 priorities/week:** P0/P1/P2 (P0 must ship).
- **Weeks 1–4:** foundation-heavy (OS2 + DS&A + Arch + OSTEP + CS:APP).
- **Weeks 5–32:** ship-heavy:
  - **Kernel:** 2 patches **SENT** weekly (proof = lore link(s)).
  - **DPDK:** 1 patch every **1–2 weeks** (proof = list/Patchwork link).
  - **Numbers artifact weekly:** script + CSV (p50/p99/p99.9 + CPU + throughput).
  - **Review SLA:** reply within 24h when feedback arrives.

---

# Phase 0 — Foundation (Weeks 1–4)

## Week 1 — Cadence + environment lock-in
**Goal:** make your study stack + OS2 environment reliable.
**Must Achieve:**
- OS2 environment boots/runs reliably (repeatable steps).
- DS&A: at least 3 short reps done.
- Arch: at least 1 concrete exercise/note block.
- OSTEP: at least 1 chapter + notes.
- CS:APP: at least 1 section + notes or small exercise.
- Numbers artifact #1 (baseline run script + baseline CSV).
**Sample Focus (flexible):** OSTEP intro/virtualization; CS:APP bits/ints; OS2 setup.
**If Lost:** fix OS2 boot/build loop first, then produce baseline benchmark file.

## Week 2 — OS2 Assignment 0 completed
**Goal:** finish OS2 Assignment 0; deepen processes/memory.
**Must Achieve:**
- OS2 Assignment 0 complete (runnable).
- DS&A: 3–5 reps + brief notes.
- Arch: 1 exercise.
- OSTEP: 1 chapter + notes.
- CS:APP: 1 section + notes.
- Numbers artifact #2 (same harness, new run, saved CSV).
**Sample Focus:** OSTEP processes; CS:APP compilation pipeline; DS&A stacks/queues.
**If Lost:** complete Assignment 0 first; everything else becomes “minimum reps.”

## Week 3 — Driver reps + concurrency start
**Goal:** build one driver-ish artifact + start concurrency literacy.
**Must Achieve:**
- OS2 driver lab progress with one “hard interface” (ioctl OR poll/blocking I/O).
- DS&A: 3–5 reps.
- Arch: 1 exercise.
- OSTEP: 1 chapter (threads/locks) + notes.
- CS:APP: 1 lab step or 1 section.
- Numbers artifact #3.
**Sample Focus:** char driver + userspace exerciser; OSTEP threads; caches overview.
**If Lost:** make the driver work end-to-end; features can wait.

## Week 4 — Tracing started + debug habit
**Goal:** start tracer (future weapon) + learn to read failures calmly. This week is lighter because the prior weeks were crazy, so I'll spend more time for AP exams.
**Must Achieve:**
- OS2 tracer skeleton runs and outputs something.
- DS&A reps done.
- Arch reps done.
- OSTEP chapter + notes.
- CS:APP progress.
- Numbers artifact #4.
**Sample Focus:** minimal kprobe tracer output; basic profiling note.
**If Lost:** “minimal output first” is the rule—no polishing until it runs.

---

# Phase 1 — Upstream Boot (Weeks 5–8)

## Week 5 — Kernel patch pipeline + 2 patches SENT
**Goal:** patch workflow becomes muscle memory.
**Must Achieve:**
- Patch pipeline written down (your checklist).
- **2 kernel patches SENT** (proof links saved).
- At least 1 review reply (even if minor).
- Numbers artifact #5.
**Sample Focus:** docs/cleanup/warnings in a single subtree.
**If Lost:** ship doc fixes; they’re fastest to merge and teach the process.

## Week 6 — First mini-series + first v2 loop
**Goal:** learn series posting and iteration.
**Must Achieve:**
- **2 kernel patches SENT** (could be 1 mini-series).
- At least one v2 (or “v2-ready” improvements if no review yet).
- Numbers artifact #6.
**Sample Focus:** 2–3 patch series under one theme.
**If Lost:** shrink scope, preserve quality, ship two independent patches.

## Week 7 — Align OS2 networking + kernel targets
**Goal:** aim work toward low-latency networking relevance.
**Must Achieve:**
- OS2 networking lab meaningful progress (runnable proof).
- **2 kernel patches SENT** biased to net/perf/tracing-ish areas.
- Numbers artifact #7.
**Sample Focus:** OS2 networking + kernel docs cleanups in net/perf docs.
**If Lost:** finish minimum OS2 networking deliverable; keep kernel streak alive.

## Week 8 — DPDK boot + first DPDK patch ready/sent
**Goal:** DPDK becomes real (without hardware excuses).
**Must Achieve:**
- **2 kernel patches SENT**.
- DPDK builds and runs one reference app.
- DPDK patch #1 prepared OR SENT (depending on readiness).
- Numbers artifact #8.
**Sample Focus:** docs/tests/cleanup around laptop-testable paths.
**If Lost:** keep DPDK scope tiny; do docs/tests if code is heavy.

---

# Phase 2 — Dual Track Output (Weeks 9–16)

## Week 9 — First DPDK patch SENT
**Goal:** active contributor in both ecosystems.
**Must Achieve:**
- **2 kernel patches SENT**.
- **DPDK patch #1 SENT** (or v2 if you already sent).
- Numbers artifact #9.
**If Lost:** DPDK doc/test patch is acceptable—ship something reviewable.

## Week 10 — Kernel mini-series #2
**Goal:** reviewers start recognizing your name.
**Must Achieve:**
- **2 kernel patches SENT** (preferably as a coherent series).
- Numbers artifact #10.
**If Lost:** do two independent patches; series later.

## Week 11 — DPDK laptop lab becomes reproducible
**Goal:** a repeatable DPDK-on-laptop workflow.
**Must Achieve:**
- **2 kernel patches SENT**.
- A reproducible DPDK run script + notes (even if no patch this week).
- Numbers artifact #11.
**If Lost:** write the run script + capture output. Proof beats complexity.

## Week 12 — Profiling discipline week
**Goal:** measurement + profiling becomes routine.
**Must Achieve:**
- **2 kernel patches SENT**.
- One profiling writeup (“bottleneck → change → new numbers”).
- Numbers artifact #12.
**If Lost:** a single useful perf/trace output + interpretation is enough.

## Week 13 — Bug-hunt attempt #1 (repro-focused)
**Goal:** learn “repro notes” muscle.
**Must Achieve:**
- **2 kernel patches SENT**.
- One bug reproduction attempt documented (success or failure).
- Numbers artifact #13.
**If Lost:** timebox 2 sessions; if no repro, switch targets next week.

## Week 14 — DPDK patch #2 or v2 loop
**Goal:** review iteration skills in DPDK.
**Must Achieve:**
- **2 kernel patches SENT**.
- **DPDK patch #2 SENT** or v2/v3 loop done.
- Numbers artifact #14.
**If Lost:** respond fast; don’t let threads go cold.

## Week 15 — Bigger kernel series (if feasible)
**Goal:** endurance + taste.
**Must Achieve:**
- **2 kernel patches SENT** (or 1 larger coherent series).
- Numbers artifact #15.
**If Lost:** quality > quantity; still meet the 2-sent quota.

## Week 16 — Midpoint packaging
**Goal:** make your proof browsable.
**Must Achieve:**
- A “midpoint summary” (links to best kernel threads, DPDK threads, and benchmark artifacts).
- **2 kernel patches SENT**.
- Numbers artifact #16.
**If Lost:** bullet list + links only. No essays.

---

# Phase 3 — Real Fixes (Weeks 17–24)

## Week 17 — Bugfix #1 target + repro locked
**Goal:** commit to one real bug.
**Must Achieve:**
- Bugfix #1 chosen + repro steps saved.
- **2 kernel patches SENT** (can be small).
- Numbers artifact #17.
**If Lost:** switch bug target fast; keep patch streak.

## Week 18 — Root cause week
**Goal:** understand the bug deeply enough to fix.
**Must Achieve:**
- Root cause hypothesis + fix draft.
- **2 kernel patches SENT** (or 1 if bugfix dominates, but aim for 2).
- Numbers artifact #18.
**If Lost:** ask a focused question on-list with logs, then continue.

## Week 19 — Send Bugfix #1
**Goal:** post the real fix.
**Must Achieve:**
- Bugfix #1 patch/series SENT + logs.
- Keep kernel cadence (at least 1 additional patch if possible).
- Numbers artifact #19.
**If Lost:** send as RFC if unsure; still ship and get feedback.

## Week 20 — Iterate Bugfix #1 (v2/v3)
**Goal:** close the loop.
**Must Achieve:**
- v2/v3 posted if requested.
- Review replies within 24h.
- Numbers artifact #20.
**If Lost:** do the smallest reviewer-requested change first, resend quickly.

## Week 21 — Meaningful DPDK patch
**Goal:** one non-trivial DPDK improvement.
**Must Achieve:**
- DPDK meaningful patch SENT.
- **2 kernel patches SENT**.
- Numbers artifact #21.
**If Lost:** “meaningful” can be tests/doc that prevent a real mistake.

## Week 22 — DPDK review loops
**Goal:** push DPDK thread to acceptance.
**Must Achieve:**
- v2/v3 responses for DPDK.
- **2 kernel patches SENT**.
- Numbers artifact #22.
**If Lost:** reply fast and keep changes small.

## Week 23 — Kernel home-base deepening
**Goal:** strengthen your chosen area (net/perf/tracing-ish).
**Must Achieve:**
- **2 kernel patches SENT** (preferably coherent).
- Numbers artifact #23.
**If Lost:** doc cleanups preserve streak and credibility.

## Week 24 — Bugfix #1 story writeup
**Goal:** turn fix into a tight narrative.
**Must Achieve:**
- Bugfix #1 story: repro → cause → fix → tests → result (1–2 pages max).
- **2 kernel patches SENT**.
- Numbers artifact #24.
**If Lost:** make it a timeline with commands + links.

---

# Phase 4 — Weapon + Packaging (Weeks 25–32)

## Week 25 — Choose your weapon
**Goal:** pick ONE tool to sharpen hard.
**Must Achieve:**
- Weapon chosen: (A) latency/measurement toolkit OR (B) tracer polished.
- v1 skeleton runnable.
- **2 kernel patches SENT**.
- Numbers artifact #25.
**If Lost:** choose latency toolkit; it aligns to HFT best.

## Week 26 — Weapon v1 usable by strangers
**Goal:** “run this” README + example output.
**Must Achieve:**
- Weapon v1 tagged/released (even informal).
- **2 kernel patches SENT**.
- Numbers artifact #26.
**If Lost:** scripts first, docs second. “Docs = run.sh.”

## Week 27 — Bugfix #2 selection + repro
**Goal:** smaller, faster second bug attempt.
**Must Achieve:**
- Bugfix #2 repro steps + fix draft.
- **2 kernel patches SENT**.
- Numbers artifact #27.
**If Lost:** switch target quickly; don’t sink weeks.

## Week 28 — Send Bugfix #2
**Goal:** ship the second bugfix.
**Must Achieve:**
- Bugfix #2 patch/series SENT + logs.
- Numbers artifact #28.
**If Lost:** send as RFC if needed; don’t stall.

## Week 29 — DPDK patch #N
**Goal:** stay active and close loops.
**Must Achieve:**
- DPDK patch or v2/v3 activity.
- **2 kernel patches SENT**.
- Numbers artifact #29.
**If Lost:** pick a doc/test gap and fill it.

## Week 30 — Kernel capstone series
**Goal:** one polished series that screams competence.
**Must Achieve:**
- Capstone kernel series posted (or 2 immaculate patches).
- Numbers artifact #30.
**If Lost:** split into smaller series; preserve polish.

## Week 31 — Final portfolio (links only)
**Goal:** one page of undeniable proof.
**Must Achieve:**
- Final link page: best kernel threads, DPDK threads, weapon, numbers artifacts, bugfix stories.
- **2 kernel patches SENT**.
- Numbers artifact #31.
**If Lost:** bullets + links. Done.

## Week 32 — Reproducibility + next 90 days
**Goal:** everything runnable; story clear.
**Must Achieve:**
- Fresh-setup reproducibility check (scripts run, artifacts regenerate).
- Next 90-day target list.
- Numbers artifact #32.
**If Lost:** fix scripts so a stranger can run them.

---
