# ProjectGenesis
(AI-assisted)
- Level-by-level, not week-by-week.
- Only “Tier S” and “Tier A” work gets real time.
- A “unit of progress” is a public receipt that helps other engineers ship safer code.

---

## The Big Goal (the one that should scare you)
Build a public record that makes a kernel or systems performance hiring manager think:
1) “This person is already operating like a senior engineer.”
2) “Wait… they are not even 20.”

**Finish line (all must be true):**
- You have multiple Linux kernel patches merged upstream.
- You closed at least one regression loop in public (reproducer → culprit or strong evidence → fix lands).
- You merged at least one automated guardrail (a test or check that prevents a class of failures from coming back).
- You ran at least one multi-patch ownership series through review, including at least one updated revision.

---

## Non-negotiable rules (so you do not waste time)
### Rule 1 — No “toy work”
If it cannot produce a public receipt (patch thread, merge, regression closure, test/guardrail merge), it is out.

### Rule 2 — Small is allowed, pointless is not
A small fix is fine if it:
- removes a real warning,
- prevents a crash,
- fixes a real incorrect behavior,
- strengthens a real test,
- or clarifies documentation that would otherwise cause a real mistake.

### Rule 3 — Receipts are the currency
Every meaningful action must create a linkable receipt:
- a public patch archive link,
- a public discussion thread link,
- a public merge reference link,
- or a public regression tracking thread link.

### Rule 4 — You must be able to certify origin
You are signing off that you understand what you are sending and that you have the right to submit it.
Never send large chunks of text you do not fully understand.

---

## Scoreboard (this is how you “weight helpfulness”)
**Tier S (maximize these):**
- Merged upstream patch (highest value).
- Regression closed with receipts (report thread + fix thread + final outcome).
- Merged automated guardrail (self test, tooling check, or code validation that prevents recurrence).
- Multi-patch series accepted or partially merged, after review and revision.

**Tier A (only if it directly increases Tier S probability):**
- Bisection to a culprit commit.
- Minimal reproducer that lets a maintainer reproduce quickly.
- A clear “before and after” measurement that supports a fix.

Everything else is noise unless it directly supports Tier S.


# LEVEL 0 — One real pipeline patch (not a toy)
## Purpose
Prove you can ship one real, mergeable fix through the Linux kernel workflow.
This is not a typo hunt. This is one real improvement plus full process proof.

## What you do (concrete)
You produce ONE patch that is both:
- small enough to review quickly, and
- meaningful enough to not feel like filler.

### Level 0 target menu (choose one)
Pick exactly one:
1) Fix a real compiler warning or build warning in a specific file you touched.
2) Fix a real checkpatch-reported issue that is not cosmetic-only (avoid the classic “line longer than 80 characters” rabbit hole).
3) Fix a real, obviously-correct correctness issue (null pointer check, error handling return path, wrong format specifier, missing bounds check), but only if you can explain it plainly.

### Level 0 workflow (Definition of “what you literally do”)
1) Get the Linux kernel source tree.
2) Create a new branch for your patch.
3) Make exactly one single-theme change.
4) Build or run the narrowest relevant check (at minimum, ensure your change compiles in the area you touched).
5) Commit with a Signed-off-by line (you certify origin and rights).
6) Generate a patch file.
7) Run the patch style checker on the patch file and fix legitimate issues.
8) Identify recipients (maintainers and mailing lists) for the file you changed.
9) Send the patch by electronic mail as inline plain text (not as an attachment).
10) Wait for the public archive link to appear and record it in RECEIPTS.md.

## Level 0 exit gate (you pass only if this is true)
- One patch is sent, archived publicly, and listed in RECEIPTS.md with:
  - the link
  - and a clear explanation of why it matters

## Why Level 0 is not a waste
If you cannot do this cleanly, “meaningful patches” later get stuck on process failure.
This level removes that risk permanently.

---

# LEVEL 1 — Merge Engine (you become “reviewable”)
## Purpose
Turn “I can send one patch” into “I can get patches accepted.”
This is where you start looking like a real upstream contributor.

## What you do (concrete)
You run a loop that produces small meaningful patches with high merge probability.

### Level 1 loop (repeat until you hit the exit gate)
1) Select a patch target that is:
   - small,
   - clearly correct,
   - and easy to test or reason about.
2) Send the patch.
3) When feedback arrives:
   - reply in-thread,
   - quote the relevant lines,
   - answer point-by-point,
   - never dodge questions.
4) If changes are requested:
   - implement the smallest fix that satisfies the feedback,
   - send a revised version (a new revision of the patch),
   - include a short “what changed since last time” section,
   - include everyone who commented so they stay in the loop.
5) Keep iterating until it is accepted, merged, or clearly rejected.

### Level 1 anti-stall rule
If you have not shipped a patch in your last two available work sessions:
- you must ship a small meaningful patch immediately (warning fix, tiny correctness fix, or a real documentation correction that prevents a real mistake).

## Level 1 exit gates (all must be true)
- You have at least two patch threads total (Level 0 plus at least one more).
- You have at least one real review interaction where:
  - someone comments and you reply correctly in-thread.
- You have sent at least one revised patch after feedback (a second submission that clearly incorporates review).

## Level 1 artifacts (must exist)
- RECEIPTS.md includes:
  - original patch link
  - review reply link
  - revised patch link (if applicable)
  - final outcome status

---

# LEVEL 2 — Merge Hunter (you collect merges, not “sent patches”)
## Purpose
A sent patch is a start.
A merged patch is what changes how serious engineers see you.

## What you do
You keep patch scope small, but you now optimize for acceptance and merge.

### Level 2 rules
- You prioritize patches that are likely to be merged:
  - small, obviously correct,
  - minimal controversy,
  - easy to validate.
- You do not “hoard” patches locally.
  If it is ready, send it.

## Level 2 exit gates
- At least one patch merged upstream.
- At least one additional patch either merged or explicitly accepted by a maintainer.

---

# LEVEL 3 — Regression Closer (you enforce “we do not cause regressions”)
## Purpose
This is a high-status skill: you help the community recover when something breaks.

## What you do (concrete)
1) Find a regression report (or observe one yourself).
2) Confirm it is a regression:
   - older kernel works, newer kernel fails or performs worse under similar configuration.
3) Produce one of the following:
   - a minimal reproducer, or
   - a bisection result pointing to a likely culprit, or
   - enough evidence that a maintainer can reproduce quickly.
4) Ensure the regression mailing list is included in the loop when appropriate.
5) Stay on the thread until there is a fix path:
   - a patch posted,
   - a revert applied,
   - or a clear maintainer-owned plan.

## Level 3 exit gate
- One regression loop closed with receipts:
  - link to regression report thread
  - link to fix (yours or someone else’s)
  - link to outcome (merged, reverted, or otherwise resolved)

---

# LEVEL 4 — Guardrail Builder (you prevent recurrence)
## Purpose
You stop fixing one instance and start preventing the class of failure.

## What “guardrail” means here
A guardrail is an automated protection that makes the bug class harder to reintroduce:
- a Linux kernel self test that fails if behavior regresses,
- a tooling or build check,
- or a code validation that turns silent wrongness into a loud failure.

## What you do
- Add or improve one guardrail tied to a real bug or regression.

## Level 4 exit gate
- One guardrail merged upstream (a self test counts, and is preferred).

---

# LEVEL 5 — Performance Change With Proof (only if it becomes upstream action)
## Purpose
Performance work is respected only when it is disciplined and ends in action.

## What you do
1) Choose a performance problem that is tied to real user impact or a clear regression.
2) Produce a repeatable measurement:
   - workload description
   - baseline numbers
   - after-change numbers
3) Translate it into upstream movement:
   - a patch
   - or a regression report that results in a fix.

## Level 5 exit gate
- One performance-related upstream outcome with receipts (patch accepted or merged, or regression closed).

---

# LEVEL 6 — Ownership Series (multi-patch, review-driven)
## Purpose
This is the strongest public signal that you can “lead” without having the title.

## What you do
- Post a coherent series of multiple patches (not one).
- Include a cover letter that explains:
  - the problem
  - the approach
  - why the series is split into these patches
  - what testing you ran
- Iterate at least once after review requests.

## Level 6 exit gate
- At least one updated revision of the series posted after feedback.
- At least one patch from the series accepted or merged.

---

# LEVEL 7 — The Shock Effect Portfolio
## Purpose
A hiring manager sees your receipts and assumes you are experienced.
Then they see your age and it becomes memorable.

## Level 7 exit gates (all must be true)
- Multiple merged upstream patches.
- At least one closed regression loop with receipts.
- At least one merged guardrail.
- At least one ownership series with revision after review and at least one acceptance.

---

# Buzzword Glossary (contextual, in plain language)

## Patch
A text representation of changes (a “diff”) that reviewers can read and comment on.

## Diff
The lines removed and added, shown in a standard format.

## Commit
A saved change in version control with an author, message, and content.

## Signed-off-by
A line in the patch that certifies you have the right to submit the change and that you understand the origin requirement.

## Developer’s Certificate of Origin
The statement you are agreeing to when you sign off.

## Maintainer
A person responsible for a part of the kernel who decides what gets accepted.

## Subsystem
A major area of the kernel (for example, networking, filesystems, scheduler, device drivers), usually with its own maintainers and mailing lists.

## Mailing list
The primary discussion and review channel for kernel development. Patch review happens here.

## Public archive link
A permanent, linkable archive of your email patch and discussion thread (commonly on lore).

## Inline plain text email
Sending the patch in the body of the email as text, not as a file attachment.

## Patch style checker
A script that flags trivial formatting and style issues in patches before reviewers waste time on them.

## Recipient selection
Choosing the correct maintainers and mailing lists so the right people see your patch.

## Review thread
The email conversation that forms when people reply to your patch.

## Interleaved reply
Replying by quoting the exact lines you are responding to, then answering below each point, so reviewers can follow you.

## Revision (revised patch)
A second submission that incorporates feedback. You keep the thread informed and show what changed.

## Regression
Something that used to work in an older kernel but fails or performs worse in a newer kernel under similar conditions.

## Bisection
A method to find the exact change that introduced a regression by testing a sequence of commits.

## Reproducer (minimal reproducer)
The smallest set of steps that reliably triggers the bug so others can confirm it quickly.

## Guardrail
An automated protection (test, tooling check, or validation) that prevents a bug class from quietly returning.

## Linux kernel self test
A small test under tools/testing/selftests meant to exercise a kernel code path and catch regressions.

## Cover letter
An introductory message for a patch series that explains the problem, approach, and testing.

## Patch series
Multiple related patches sent together as a coherent unit.

___

- Linux kernel patches are submitted by email and preferably inline text; attachments are generally frowned upon. 

- You should identify and include maintainers and lists; scripts/get_maintainer.pl is recommended in the submitting patches guide. 

- Checkpatch is an official tool for trivial style violations (and your judgment matters). 

- Regressions have an official reporting and handling process, including the regression mailing list and regzbot guidance. 

- Linux kernel self tests live under tools/testing/selftests and are intended to exercise individual code paths (a core “guardrail” mechanism). 

- For first patches, KernelNewbies guides exist and also warn against low-value “line longer than 80 characters” fixes.

## Final State Visualization (what “done” looks like)
This is the concrete, linkable end state of ProjectGenesis.

### Level mapping (how it fits together)
- Level 0: proves the pipeline works (first real patch sent + archived link)
- Level 1: proves review survival (at least one real review interaction + at least one revision)
- Level 2: proves merges (first merged patch + second accept/queue/merge signal)
- Level 3: proves regression closure (a regression report thread that ends in a fix outcome)
- Level 4: proves prevention (a merged guardrail: a self test or automated check)
- Level 6: proves ownership (a reviewed multi-patch series + v2 + at least one acceptance/merge)
- Level 7: proves “shock effect” (you have enough receipts that you look experienced)

### Minimum “Level 7 Complete” end state (smallest acceptable finish line)
By the time Level 7 is complete, I can point to:
- 3 upstream merged Linux kernel patches (public links)
- 1 additional patch accepted or queued by a maintainer (public link)
- 1 regression loop closed with receipts:
  - regression report thread link
  - fix thread link
  - final outcome link (merged fix or equivalent resolution)
- 1 merged guardrail (a self test or automated check) that prevents recurrence
- 1 ownership patch series (4–8 patches) with:
  - a cover letter
  - at least one revised version (v2) after review
  - at least 1 patch from the series accepted or merged

### “Awe” end state (what makes serious engineers pause)
If I push beyond the minimum, the “awed” finish line looks like:
- 8–15 upstream merged Linux kernel patches
- 3–6 additional patches accepted or queued
- 2–4 regression loops closed (at least one with a reproducer or a bisection result)
- 2 merged guardrails (at least one being a Linux kernel self test)
- 2 ownership series total:
  - one 4–8 patch series with at least 2 patches accepted/merged
  - one 3–5 patch series with at least 1 patch accepted/merged
  - both with cover letters and at least one revised version

