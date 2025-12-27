# ProjectGenesis 
(AI-assisted)
- Level by level, not week-by-week deadline.
- I also work on a foudation phase(D&A, CS:APP, OS:3EP, OS2(Linux kernel), TCP-IP Illustrated Vol I + Unix Network Programming), which I should not rush and build a solid ground before going forward.
# LEVEL 0 — Operator (you can run the entire pipeline end-to-end)

## Purpose
Become operational so you stop wasting willpower on setup friction.
Level 0 is about “I can do the motions without guessing.”

## Entry conditions
- You can build the Linux kernel (at least enough to compile the touched subsystem).
- You have working electronic mail sending from the command line for patches.

## Priority loop while you are in Level 0 (every iteration)
### Priority 0
- Produce one “end-to-end dry run” proof pack that shows you can:
  1) create a patch
  2) run the patch style checker
  3) identify maintainers and mailing lists
  4) send as plain text electronic mail
  5) collect a baseline benchmark run
  6) collect a performance counter summary
  7) collect a recorded kernel trace
  8) apply and remove network emulation impairment

### Priority 1
- Repeat the same pipeline with a second patch (even a documentation-only patch).

### Priority 2
- Build and run one Data Plane Development Kit reference sample and record commands.

## Level 0 exit gates (Definition of Done)
You pass Level 0 only when all are true:

### Gate 0.1 — Linux kernel patch mechanics are real (not theory)
You can do all steps, in this order, without improvising:
1. Make a small, single-theme change.
2. Generate a patch file using Git.
3. Run the Linux kernel patch style checker script on the patch file.
4. Run the maintainer identification script to generate recipients.
5. Send the patch using Git electronic mail sending, as **inline plain text**, not as an attachment.
6. Save:
   - the Message Identifier from the sent mail
   - the public archive link when it appears
   - the exact commands you ran

### Gate 0.2 — Performance measurement basic competence
You can produce and archive:
- A baseline run output (your workload choice, but it must be repeatable).
- A performance counter statistics capture using `perf stat` for the workload.
- A recorded profile or at minimum a recorded statistics file (if you use `perf stat record`, archive the output file).

### Gate 0.3 — Kernel tracing basic competence
You can:
- record a trace using `trace-cmd record`
- produce a readable trace output (for example, with a reporting command)
- explain in one paragraph what you traced (for example: scheduling events, wakeups, or a specific tracepoint).

### Gate 0.4 — Network emulation competence
You can:
- apply fixed delay
- apply jitter
- apply packet loss
- remove the impairment cleanly
- prove the impairment happened (for example, by showing the configuration you applied and the measured effect).

### Gate 0.5 — Network interface feature visibility
You can query and record the network interface feature and offload state using Ethernet tool “show features” output.

## Level 0 artifacts (must exist before you leave Level 0)
- `LEVEL_0_PROOF.md` with:
  - commands (copy-paste runnable)
  - links (public archives for patch)
  - outputs (or paths to outputs)
- One baseline `results.csv` and one `run_benchmarks.sh`
- One `perf_stat.txt` capture
- One trace output file (whatever `trace-cmd record` produced on your system)

---

# LEVEL 1 — Public Contributor (you send patches and you measure every time)

## Purpose
Stop “preparing to contribute.” Start contributing consistently.

## Entry conditions
- You passed Level 0.

## Priority loop while you are in Level 1 (every iteration)
### Priority 0 (must ship)
1) **Send at least one Linux kernel patch** (public link recorded).  
2) **Ship one numbers artifact** (script + comma-separated values + interpretation note).  
3) **Run one network impairment scenario** (fixed delay or jitter) and include it as a second row (or second configuration) in the comma-separated values.

### Priority 1 (should ship)
- Send the second Linux kernel patch.
- Reply to any reviewer feedback within one day if feedback arrives.

### Priority 2 (nice to ship)
- Build and run one Data Plane Development Kit reference sample again and capture baseline throughput and latency percentiles.

## Level 1 exit gates (Definition of Done)
You pass Level 1 only when all are true at least once:

### Gate 1.1 — Two Linux kernel patches sent
- Two separate patches are sent as plain text electronic mail.
- You can point to the public archive links for both.
- You can show the exact commands used to generate and send them.

### Gate 1.2 — One real review interaction
- You receive feedback on at least one patch and reply in-thread.
- Your reply is interleaved and trimmed (not top-posted).
- If the reviewer asks for change, you acknowledge what you will change.

### Gate 1.3 — One complete performance case study (small but real)
One “before and after” case study must exist that includes:
- baseline numbers (50th percentile latency, 99th percentile latency, 99.9th percentile latency, throughput, Central Processing Unit utilization)
- one change (one patch or one configuration change)
- after numbers (same set)
- one paragraph explaining what changed and why (based on evidence, not vibes)

### Gate 1.4 — One impairment comparison
You must show at least one comparison:
- baseline (no impairment)
- impaired (fixed delay or jitter)
- measured change in 99th percentile latency and 99.9th percentile latency

## Level 1 patch menu (so you do not stall)
Pick work that is small and reviewable:
- documentation fixes in Linux kernel networking documentation
- selftest improvements (tests are high-signal and reviewers like them)
- obvious error handling improvements (single function, single file)
- build warning fixes limited to one subsystem

## Level 1 anti-stall rule
If you have not sent a patch in 48 hours of available work time:
- immediately send a documentation-only patch to restore momentum
- then go back to harder patches

---

# LEVEL 2 — Two Ecosystems (first Data Plane Development Kit patch sent)

## Purpose
Become publicly active in both:
- Linux kernel upstream
- Data Plane Development Kit upstream

## Entry conditions
- You passed Level 1.

## Priority loop while you are in Level 2 (every iteration)
### Priority 0
- Send at least one Linux kernel patch.
- Ship numbers artifact with two configurations (baseline + one change).

### Priority 1
- Send the second Linux kernel patch.
- Keep review response within one day if feedback arrives.

### Priority 2 (this is the Level 2 differentiator)
- Prepare and send a Data Plane Development Kit patch (documentation or tests are fine).
- Include a cover letter if it is a patch series.

## Level 2 exit gates (Definition of Done)
### Gate 2.1 — One Data Plane Development Kit patch sent correctly
- You send a patch to the Data Plane Development Kit mailing list using Git electronic mail sending.
- You can show the public link for the patch.
- If it is a series, you include a cover letter.

### Gate 2.2 — Data Plane Development Kit build and run is reproducible
- You can build Data Plane Development Kit from scratch on your machine.
- You can run one reference sample application.
- You have a “copy-paste commands” log that reproduces it.

### Gate 2.3 — Numbers artifact includes a real systems knob
Your two-configuration comparison must include at least one of:
- batch size
- worker thread count
- core pinning policy (even if crude)
- network impairment intensity (for example: fixed delay vs jitter)
- network interface feature state difference (if you toggled any offloads)

## Level 2 Data Plane Development Kit patch menu
Start with contributions that are maximally reviewable on any machine:
- documentation clarifications
- tests
- build system improvements
- small correctness fixes that do not require specialized hardware

## Level 2 anti-stall rule
If Data Plane Development Kit patch is “almost ready” for more than one iteration:
- you must either send it as-is (small scope) or abandon and pick a smaller one
- you are not allowed to “hold” a patch forever

---

# LEVEL 3 — Repeatable Latency Laboratory (control the network, prove cause and effect)

## Purpose
Become a person who can say:
“I can reproduce the latency behavior, change one knob, and the percentiles move in a predictable direction.”

## Entry conditions
- You passed Level 2.

## Priority loop while you are in Level 3 (every iteration)
### Priority 0
- Numbers artifact must contain:
  - baseline
  - impaired
  - recovered (impairment removed)
- At least one Linux kernel patch sent.

### Priority 1
- Second Linux kernel patch sent.
- One trace capture using `trace-cmd record` during either impaired or recovered run.

### Priority 2
- Data Plane Development Kit patch progress (send if ready, or prepare version two if review asked for changes).

## Level 3 exit gates (Definition of Done)
### Gate 3.1 — You can run multiple network impairment scenarios
You must demonstrate with numbers:
1) fixed delay
2) jitter
3) packet loss
4) rate limiting (if your setup supports it reliably)

For each scenario you must include:
- baseline run
- impaired run
- recovered run

### Gate 3.2 — Network interface feature state is captured every time
For each benchmark run you keep:
- the Ethernet tool “show features” output
- a short note: “did feature state change this week”

### Gate 3.3 — One tail-latency spike is investigated with kernel tracing
You must produce one mini-investigation:
- symptoms: what percentile moved and under what impairment
- trace capture: what you recorded (events)
- hypothesis: what subsystem is implicated (scheduling, interrupt handling, soft interrupt processing, queueing)
- one mitigation experiment: what you changed next

### Gate 3.4 — Benchmarking discipline: you do not lie with numbers
You must explicitly avoid “latency at maximum load” claims.
Your report must state:
- the throughput point you measured at
- that it is below the knee of the throughput–latency curve
- whether load generation is open-loop or closed-loop

---

# LEVEL 4 — Real Bugfix Loop (reproduce → isolate → fix → iterate in public)

## Purpose
This is where you stop looking like “a patch sender” and start looking like “an engineer who closes loops.”

## Entry conditions
- You passed Level 3.

## Priority loop while you are in Level 4 (every iteration)
### Priority 0
- One bugfix investigation log that ends in:
  - either a sent fix
  - or a documented “ruled out” conclusion with evidence
- One Linux kernel patch sent (if bugfix dominates, the patch can be small).

### Priority 1
- Second Linux kernel patch sent (or a smaller patch if the bugfix is heavy).
- Reply to review within one day.

### Priority 2
- Data Plane Development Kit patch iteration or a new small patch.

## Level 4 exit gates (Definition of Done)
### Gate 4.1 — One complete bugfix story exists
Your story must include:
1) reproduction steps that another person could run
2) evidence (logs, trace output, or both)
3) root cause hypothesis
4) fix patch or fix patch series sent
5) at least one updated version (version two or later) sent due to feedback

### Gate 4.2 — One performance win exists with profiling evidence
A performance win must include:
- baseline numbers
- after numbers
- `perf stat` evidence
- either a recorded profile or a trace capture that supports your explanation
- one paragraph: why this change should plausibly improve performance (cache behavior, branch behavior, fewer wakeups, fewer queueing points, reduced contention, and so on)

### Gate 4.3 — Timeboxing discipline (you do not disappear into a rabbit hole)
You must demonstrate that you:
- timeboxed a failed reproduction attempt
- switched targets when needed
- still shipped at least one patch per iteration

---

# LEVEL 5 — Kernel Bypass Credibility (fast packet processing that is measured and explained)

## Purpose
This level exists because elite low-latency infrastructure roles explicitly value:
- kernel bypass familiarity
- user-space networking
- performance counter-driven optimization
- measurement competence

## Entry conditions
- You passed Level 4.

## Priority loop while you are in Level 5 (every iteration)
### Priority 0
- Numbers artifact must include at least two fast-path configurations and their percentiles.
- At least one Linux kernel patch sent.

### Priority 1
- Second Linux kernel patch sent.
- Data Plane Development Kit patch thread activity (either new patch or responding to review).

### Priority 2
- One deeper measurement or trace pass aimed at explaining why 99.9th percentile latency moved.

## Level 5 exit gates (Definition of Done)
### Gate 5.1 — Data Plane Development Kit series receives real review
You must have:
- a coherent patch series (not just a single patch)
- at least one reviewer comment
- at least one response from you
- if requested, an updated version (version two or later)

### Gate 5.2 — Fast-path experiment matrix exists (measured, not guessed)
You must compare at least two of the following dimensions:
- batch size
- worker thread count
- core pinning policy
- network interface feature state (offloads on versus off, if you change it)
- network impairment mode (fixed delay versus jitter versus loss)

For each configuration you record:
- 50th percentile latency
- 99th percentile latency
- 99.9th percentile latency
- throughput
- Central Processing Unit utilization

### Gate 5.3 — You can explain kernel bypass tradeoffs in plain language
One written explanation must exist:
- what kernel bypass provides (lower overhead in the kernel networking stack path, different batching model, direct device access patterns)
- what it costs (device binding complexity, different debugging model, different driver model constraints, risk of misleading measurements if offloads change)
- where latency hides (interrupt handling, soft interrupt processing, queueing, batching, cache effects, scheduling)

---

# LEVEL 6 — Upstream Tooling or Test Improvement Accepted (high-value, not a hobby project)

## Purpose
You wanted late levels to be directly resume-relevant.
This level is resume-relevant because it demonstrates you improve:
- correctness guardrails
- tooling
- automation
- testing discipline

## Entry conditions
- You passed Level 5.

## Priority loop while you are in Level 6 (every iteration)
### Priority 0
- Keep at least one Linux kernel patch sent plus numbers artifact (do not lose momentum).

### Priority 1
- Drive one upstream acceptance lane hard (Linux kernel or Data Plane Development Kit).

### Priority 2
- Continue Data Plane Development Kit patch cadence (or iteration) so both ecosystems stay alive.

## Level 6 exit gates (Definition of Done)
Choose exactly one lane and complete it:

### Lane A — Linux kernel lane
- One accepted patch that improves one of:
  - tooling or automation
  - selftests or test coverage
  - documentation that prevents a real mistake
- Evidence of acceptance (maintainer “applied”, “queued”, or merged into a public branch).

### Lane B — Data Plane Development Kit lane
- One accepted patch that improves one of:
  - tests
  - build correctness
  - continuous integration guardrails
  - developer tooling that makes changes safer
- Evidence of acceptance (maintainer “applied”, “queued”, or merged).

Level 6 is passed only when acceptance is real and linkable.

---

# LEVEL 7 — Ownership Under Fire (coherent multi-patch series, review-driven iteration, evidence)

## Purpose
This is not a recap of earlier levels.
Earlier levels prove you can send and land patches.
This level proves you can **lead** a coherent upstream mini-project:
- scope it
- communicate it
- survive feedback
- ship updates
- land a meaningful subset
- attach honest evidence

## Entry conditions
- You passed Level 6.

## Priority loop while you are in Level 7 (every iteration)
### Priority 0
- Continue shipping baseline numbers artifacts (do not stop measuring).

### Priority 1
- Continue shipping Linux kernel patches (at least one per iteration), even if small, to keep upstream presence.

### Priority 2 (the Level 7 differentiator)
- Push the ownership series forward: cover letter, patch series, version two, acceptance.

## Level 7 exit gates (Definition of Done)
Choose one lane and complete all requirements.

### Lane A — Linux kernel ownership series
You must complete all of the following:

1) **Series size and coherence**
- Post a coherent series of **four to eight patches**.
- Include a cover letter that explains:
  - the problem
  - the approach
  - why the series is structured the way it is
  - what testing you ran

2) **Series scope is non-trivial but sane**
- The series must touch at least:
  - two files, or
  - two logical components

3) **Public review-driven iteration**
- You must send at least one updated version (version two or later) because reviewers requested changes.
- Your cover letter includes a clear change log of what changed since the previous version.

4) **Acceptance signal**
- At least two patches from the series are accepted, applied, or merged.
- You capture the evidence link(s).

5) **Evidence attached**
- If performance-related:
  - attach numbers artifact before and after that shows what moved
- If correctness or tooling related:
  - attach “no regression” numbers artifact plus test evidence

### Lane B — Data Plane Development Kit ownership series
You must complete all of the following:

1) **Series size and coherence**
- Post a coherent series of **three to six patches** with a cover letter.

2) **Guardrails included**
- At least one patch in the series improves:
  - tests, or
  - documentation that prevents mistakes, or
  - an automated check

3) **Public review-driven iteration**
- You must send at least one updated version (version two or later) due to reviewer feedback.

4) **Acceptance signal**
- At least one patch is accepted, applied, or merged with evidence.

5) **Measured outcome**
- Include a before/after numbers artifact showing:
  - 50th percentile latency, 99th percentile latency, 99.9th percentile latency
  - throughput
  - Central Processing Unit utilization

## Mandatory “edge” pressure test (pick one)
To pass Level 7 you must also do one of these:

1) Write a 200–400 word explanation that a maintainer could forward to another maintainer as the justification for the series.
2) Run an additional scenario that could have regressed and prove it did not regress (example: different message size, different worker thread count, different impairment mode).
3) Demonstrate benchmarking discipline explicitly:
   - show that your main measurement point is below the knee of the throughput–latency curve
   - state whether your load generator is open-loop or closed-loop

---

# Optional: Personal Capstone (only after Level 7, not required for passing)

After Level 7, you are allowed to choose any personal project at any scale you want.
It is optional because at that point your public upstream proof already speaks for itself.

