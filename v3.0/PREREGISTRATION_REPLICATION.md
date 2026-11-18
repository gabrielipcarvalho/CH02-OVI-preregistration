# Pre-registration v3.0: a replication of the new-literature test, with an exploratory test of the stated operator rules

**Status: prepared 18 November 2026; binding from its publication by Gabriel as v3.0.** Provenance: agent:claude-opus-5-5 (Goal A,
`docs/rerun-2026-11/`). It is to be published as **v3.0** of `gabrielipcarvalho/CH02-OVI-preregistration`,
together with [REPORTING_RULES_REPLICATION.md](REPORTING_RULES_REPLICATION.md), **before the freeze and before
the first rated request**. The push is Gabriel's. Nothing in either document changes after publication; any
later departure is a dated deviation.

## Why this test

The new-literature test of v2.0 (PREREGISTRATION_POSTSLR.md and its stage 2 amendment) is not clean
confirmatory evidence:

- It stopped at request 558 of 684 on an OpenAI HTTP 520 that the pre-registered policy (DEC-0011) says is
  re-requested, but the transport did not then retry it.
- The stopped comparison (31 paper-executions, 26 papers) is its pre-registered result: −2.4 points
  [−14.3, +8.1], *not detected*. That subset was atypical in its paper mix.
- The run was then resumed as a declared deviation, decided after the stopped result was known. The completed
  comparison gave +7.2 [+0.2, +13.8]. Its reporting rules were written during the run.

This test asks the same question again on the same papers, with every rule, measure, stopping condition and
reporting sentence fixed before any request. It does not replace the v2.0 result: v2.0's results and
readings stay as published, the stopped comparison stays the primary result of that test, and this test is
reported separately with its own reading.

A second question rides on the same run. Every arm of every earlier test stated how the criteria's operators
combine (a semicolon joins requirements that must all be met; an explicit OR offers alternatives) in its
procedure or rubric, so the study never measured what raters do without that statement. One added arm removes
both operator rules from the v1.0 procedure.

## Questions

1. **Confirmatory (replication).** Does the refined rubric (v1.2 revision 3 with procedure H5) let three
   independent AI raters resolve more panels than the published rubric (v1.0 with the original procedure) on
   the 57 papers published after the SLR?
2. **Exploratory (ablation).** Under v1.0, does removing the procedure's two sentences on how semicolons and
   OR combine change what the raters resolve and score?

## Arms

One run, three arms; the only differences are the rubric and the procedure.

| Arm | Rubric (sha256) | Procedure (sha256) | Role |
|---|---|---|---|
| `REPL_V12` | `rubric/rubric_v1_2_r3.yaml` (`7de3e76f46b407f70a1b46642fb1d36914c8a6662415641e8fc5dcb13757fa5c`) | `HANDBOOK_H5.txt` (`c18d59968bcce0720a2c8c481e18356cfd9d3bccd14d2cc5235f1586d7329154`) | refined (confirmatory) |
| `REPL_V10` | `rubric/rubric.yaml`, the published v1.0 (`df5d7b4b6ff301e995818c68f75f896e46b28dfcd3df3e0f909dd590f11047f3`) | `HANDBOOK_EVAL_ORIGINAL.txt` (`b1f05abc025df5effd2d6505a1456d5308637af6c7bee860637b6fe8ef88760c`) | published (confirmatory; control for the ablation) |
| `REPL_V10_NOCONJ` | `rubric/rubric.yaml` (as above) | `HANDBOOK_EVAL_ORIGINAL_NOCONJ.txt` (`c4dae86198cac755ed830979190c54c01e555946158784552a2541e77611fd2a`) | ablation (exploratory) |

Each procedure file is appended to the common AI-only protocol (`calibration/protocol-ai-only-v1.md`,
`9df1c6b9e738d91a3b076caeea9121bfd02cbd683f3ed2d004b33b13b9dda42e`), as in every earlier test. All files are in
`gabrielipcarvalho/CH2-Framework-Validation` at the commit named in the release.

**The ablation's procedure** is the original procedure with exactly two sentences removed, and nothing else
changed (2,068 → 1,943 bytes):

```
13,14c13
< published criterion. Semicolon-separated joint requirements are conjunctive. An explicit OR
< allows its stated alternatives; preserve that choice. Assess the criterion as written rather
---
> published criterion. Assess the criterion as written rather
```

- **What stays in it: three residuals, named in advance (decision D42 in the repository).** The two removed
  sentences are the only ones that state the semicolon and OR rule. Three sentences that bear on it stay,
  because each also does other work, and removing them would change more than the stated rule:
  1. "For any proposed level, identify source support for every component required by that level's published
     criterion." It implies that every required component needs support, but not which components a
     semicolon or an OR makes required.
  2. "Documented cost and LMIC-related requirements remain separate where the criterion requires both." It
     applies only where a criterion already requires both, and also guards against one requirement standing in
     for the other.
  3. "Apply the exact criterion and its alternatives; report only evidence supported by the source." It closes
     the P4 paragraph on privacy-mitigation examples and restates, in general terms, that alternatives exist.

  A general instruction common to every arm also stays in the protocol: "Scorable ambiguity uses the
  conservative lower supported level" (`calibration/protocol-ai-only-v1.md`, lines 12–13). The ablation
  therefore tests the removal of the explicit rule, not of every cue to it. A null result cannot
  show that raters read the criteria correctly without any cue.
- **Nowhere else in the v1.0 prompt is the rule stated.** A scan of every other part of the prompt (the prompt
  template, rubric v1.0, the common protocol, the final check, the response schema, the quote-correction and
  repair steps) finds no statement of the semicolon or OR rule. In the v1.0 arms the criteria keep their
  published wording, including their uppercase OR and semicolons. (v1.2 revision 3 rewords P4 level 0, which
  uses "and" instead.)
- **v1.2 revision 3 is not ablated.** Its rubric states the rule itself, under the pillars' common text:
  "Within a level, requirements separated by semicolons must all be met; an explicit OR offers alternatives,
  any one of which suffices. Each level is assessed as written: the descriptions of lower levels are not added
  as further prerequisites." (`rubric/rubric_v1_2_r3.yaml`, line 31). The ablation therefore speaks to v1.0 only.

## Fixed in every arm

These are the settings of the completed v2.0 run, after its code amendment of 12 November 2026, with the
transport changes made since (Goal A, 18 November 2026), which only decide what happens when a reply or a
request fails:
- a billing error recognised by code or by the words above is never retried;
- a malformed reply (non-object cells or defence, a one-line fence, a non-string pillar, an escaped lone
  surrogate) is recorded as a failure, where it used to crash the runner;
- a reply the ledger cannot store is recorded as "Unstorable provider reply";
- an interruption during a format-recovery turn parks the request, where it used to re-request it.

The settings themselves:

- **Raters:**
  - gpt-6.1-sol, reasoning effort low, not stored;
  - glm-5.3, thinking on, reasoning effort high, JSON mode;
  - claude-sonnet-5-5, effort medium.
  - Each rater has a 16,000-token output cap and receives the final check v2 (`FINAL_CHECK_V2.txt`,
    `978662ad62aeaf772b8ab19ddeb914c44a514e530103f1f0403e388dc43c638f`).
- **Inputs:** the md-v1 Markdown with the frozen figure descriptions published in v2.0. Each paper's PDF and
  rater text must match `INPUTS_POSTSLR.json` (`dbaf371869d00fadadd3e8bdafdd010ebd0629af1fea2c364430fb3e1a8da0d3`);
  a packet whose bytes differ is refused.
- **Pipeline:**
  - validator md-page-v1.3 with the adjacent-page rule;
  - quote-correction-v1 (one quotation correction turn);
  - glm-repair-v2.
- **Re-request policy: `unreadable-resample-v4`.**
  - Every HTTP 5xx and other transient failure is retried by the transport, up to three attempts.
  - A failure that shows nothing of the judgment (wholly unreadable, incomplete, or a provider failure that
    outlasts the transport) is then re-requested up to three times, unchanged.
  - A quota or billing error is never retried. One is recognised by a known code (including Z.AI's 1113) or by
    a message that contains any of the words balance, credit, quota, billing, payment, arrears or
    insufficient (so, for example, "insufficient capacity" also counts as a billing error).
  - A provider or transport failure that outlasts all of these stops the run (see "Stopping rules"). An
    unreadable or incomplete reply that outlasts them is a recorded outcome, and the run carries on.
- **No discussion stage.** Independent round (R0) only. The arms are frozen without the discussion policy, so
  the ledger refuses any later round.
- **Blinding:** each rater receives only the paper, the rubric and the procedure, in separate stateless
  requests.
- **Model identity:** if a pinned model is retired or returns a different identity, the run stops (below). No
  model is substituted.
- **Code:** the freeze and the run use the pipeline code whose file hashes are listed in the release
  (`CODE_HASHES.json`). The runbook checks this before the freeze and the launch (`build_prereg_release.py
  --check-code`) and does not launch if any file differs. The runner itself refuses a launch whose code
  differs from the code recorded at the freeze.

## Papers

- **The set:** the same 57 papers as v2.0, listed with their study IDs and hazard-detector flags in its stage 2
  amendment, at the same input hashes. 14 are hazard detectors (DEC-0010), flagged at screening before any
  rating.
- **Checked:** a dry-run freeze on a copy of the ledger (18 Nov 2026) re-verified all 57 inputs against the
  published hashes.
- **Exposure (disclosed):**
  - These papers are not new to the study. The same three models rated them in the v2.0 run, through
    separate API requests that keep no memory between calls.
  - The analyst and Gabriel know the v2.0 results on them.
  - No rubric text, procedure text or analysis choice in this document was written to change a result on a
    particular paper. The two versions compared are unchanged since before v2.0; the only new text is the
    ablation's deletion.
  - This is a replication of the procedure on the same papers. It is not a test on unseen papers.
  - The v2.0 screening correction (drafted 13 Nov 2026 for that repository) applies here too. The assistant
    that screened these papers had also drafted the rubric revisions, and its screening notes anticipated how
    some papers would fall under the v1.2 scope statement. The scope make-up of the set was therefore known
    before v2.0's run.

## Design

- **Executions:** two new executions per arm, numbered 1 and 2 within each new condition. Each is a new run,
  distinct from every earlier run.
- **Requests:** 57 papers × 2 executions × 3 arms × 3 raters = **1,026 requests**, that is 342 per arm and 342
  per rater.
- **Order:** one schedule interleaving all three arms, in a seeded random order. The seed is
  **`ch2-repl-20261120`**: the runner shuffles each run's requests, then shuffles the three arms' requests
  together with this seed (`freeze_repl` in `pipeline/study/final_phase.py`).
- **Freeze:** run IDs are hashes of each run's manifest, which includes the code commit, so the IDs and the
  exact request order are produced by the freeze. Before launch they are recorded with the sha256 of
  FREEZE.json, in the run log of `docs/rerun-2026-11/goal-b/`.
- **Dry run:** a dry-run freeze on a copy of the ledger, with the released pipeline code
  (`DRY_RUN_FREEZE.json` records its code hashes), gave 1,026 requests in three interleaved arms. None of its
  run IDs matched any of the 75 earlier frozen runs.
- **First call:** the smoke run `D0_REPL` (the fictional fixture, v1.2 revision 3 package, 3 requests, R0
  only) must pass for all three raters before the first real request.
  - If it fails, the run is not launched. Gabriel decides what happens next, and any change made before the
    launch is a dated deviation.

## Measures

A **panel** is one paper × one pillar × one execution. A panel is **resolved** when the three raters give the
same score, each backed by a verified quotation or the absence marker, or all three give the same non-scored
status (in practice "not applicable"; the classification is v2.0's, `discussion_report.classify`). **Complete and agreeing** means three identical scores.

**Rows:** each comparison uses the panels of the paper-executions complete in **its own two arms**: the
confirmatory comparison those complete in `REPL_V12` and `REPL_V10`, the ablation those complete in
`REPL_V10_NOCONJ` and `REPL_V10`. When the run completes, both use all 456 panels. After a stop, the confirmatory
comparison does not lose rows to the exploratory arm. A request that ended in a recorded failure counts as
complete, and its panels count as unresolved.

### Confirmatory comparison: `REPL_V12` minus `REPL_V10`

- **Primary (as in v2.0):** the paired difference in the proportion of resolved R0 panels, executions pooled.
  - **Interval:** 95% percentile interval from a paper bootstrap (10,000 resamples, seed
    `ch2-repl-20261120`).
  - **Also reported:** the discordant pairs in each direction.
- **Three-way reading (as in v2.0):**
  1. **Transfers:** the lower bound is above 0.
  2. **Not detected:** the interval includes 0.
  3. **Reverses:** the upper bound is below 0.
- **Equivalence reading (added), with a bound of ±10 percentage points** (decision D43).
  - **What the bound is.** A bound chosen for feasibility. If the true difference is 0, the design excludes
    ±10 with about 77% probability (standard error about 3.5 points, from the completed v2.0 run's
    precision); a ±8 bound would give about 50%. It is not a claim that smaller differences are unimportant:
    a difference of 7 or 8 points, as in earlier tests, would matter. The reading is therefore named "within
    the bound", not "equivalent".
  - **How it was chosen.** It was set after the v2.0 results on these same papers were known (completed
    comparison +7.2, 90% interval [+1.5, +12.9]). At that time:
    - two executions of the same arm differed by 0.4 and 2.6 points;
    - the expected 90% half-width with 57 papers and two executions is about 6 points, so a ±5 bound could
      not be met even with no true difference;
    - ±10 lies below the exposed-corpus gain that motivated this test (+16.7 [+11.0, +22.9]). That gain came from
      a different paper mix (3 of 42 hazard detectors there, 14 of 57 here) and an earlier re-request policy
      (v3), so the two are set side by side, not compared as a test.
  - **The readings,** from the 90% interval of the same bootstrap draws, compared before rounding:
    - **Within the bound:** the interval lies strictly inside (−10, +10), which amounts to two one-sided tests
      at 5%. The text says "differences of 10 points or more are excluded by the 90% interval".
    - **Beyond the bound:** the interval lies wholly at or above +10, or wholly at or below −10.
    - **Not shown:** any other result.
  - It is reported beside the three-way reading. For example, "transfers" with "within the bound" means a gain
    smaller than 10 points.
- **Added measures.** Each is a paired difference with the same 95% and 90% intervals, except 6 (a test) and
  7 (an interval):
  1. Complete and agreeing panels.
  2. The kind of agreement: resolved panels agreed at level 0, agreed above 0, and agreed not applicable,
     each as a paired difference with its intervals.
  3. Identical scores on panels all three raters scored in both arms, and the same without P3.
  4. Scope agreement:
     - per paper-execution: each rater's call from P1–P3 (all scored = in; none scored = out), with agreement
       meaning three identical in/out calls;
     - per panel: no failed judgment, and all three raters scored or all three did not.
  5. The primary measure, and complete and agreeing, without the 14 hazard-detector papers, with the three-way
     rule applied to the former as a sensitivity reading.
  6. A paper-level sign-flip permutation test of the pooled difference in resolved panels (20,000 flips, seed
     `ch2-repl-20261120`, two-sided), and the exact sign test on papers.
  7. A bias-corrected and accelerated (BCa) interval from the same draws (sensitivity of the interval only).
- **Declared biases of the primary.**
  - **Agreed "not applicable".** Resolved panels include panels all three raters judge not applicable.
    v1.2 revision 3 adds a scope statement and rules, so it can produce more agreed "not applicable" by design.
  - **The floor.** Most scores are 0, and agreeing at 0 is easy (as v2.0 noted). In the completed v2.0
    comparison the whole gain was agreement at 0 and agreed not applicable (291 vs 271 panels at 0, 43 vs 22
    not applicable); agreement above 0 fell (21 vs 29). An arm that scores above 0 more often is therefore
    penalised by the primary. This applies to the ablation arm too.
  - **Scope agreement.** H5 tells raters that "P1, P2 and P3 are either all assessed or all not applicable".
    The per-paper-execution scope measure counts a call only when it is all-or-none, and the per-panel
    measure partly does the same, so both favour v1.2 revision 3 by design. They are reported as such.
  - **Complete and agreeing (measure 1).** Resolved panels minus agreed "not applicable" (in v2.0, 355 − 43
    = 312 and 322 − 22 = 300). So it falls, by construction, for the arm that produces more agreed "not
    applicable", which is v1.2 revision 3 by design.
  - **Failed judgments.** A panel with a failed judgment counts as unresolved. So a difference in failure
    rates between arms (for example truncated or incomplete replies on the longer v1.2 revision 3 + H5
    prompt) enters the primary as disagreement. The paired difference in panels with a failed judgment is
    reported beside the primary.
  - **Identical scores on fully scored panels (measure 3).** These are conditional on all three raters scoring
    in both arms, so they compare agreement on a selected set of panels, and they inherit the floor (most such
    panels are at 0). In v2.0 they gave +13.8.
  - **What follows.** Measure 2 makes the three kinds of resolution paired measures with intervals, so a gain
    made only of agreement at 0 or of "not applicable" is visible. The reporting rules qualify the headline
    by them, and they state these biases wherever measures 1, 3 and 4 are reported, the abstract included.
- **Descriptive only:**
  - resolved panels by pillar;
  - panels with a score above 0 (at least one rater gave a checked score above 0), as a paired difference.
    It works against v1.2 revision 3 by construction, since that arm produces more agreed "not applicable";
  - agreement beyond 0;
  - agreed levels and every level given;
  - papers agreed out of scope;
  - repeat stability between the two executions;
  - coverage (share of valid judgments);
  - request paths (first attempt, format recovery, quotation correction, re-requests);
  - failures by outcome;
  - cost per provider;
  - the OVI-Gate of every agreed four-pillar profile (as in v2.0);
  - the effect sizes beside the earlier tests' (in the article's Figure 2, side by side, not compared
    formally, with the confounds named).

### Exploratory ablation: `REPL_V10_NOCONJ` minus `REPL_V10`

- **Measures:** the same as for the confirmatory comparison, with the same seed and intervals, on its own
  rows (above). Resolved panels, panels with a score above 0, and resolved panels by pillar are the measures
  the reporting sentence uses.
- **What it can and cannot show.** Removing either sentence can move scores in either direction, depending
  on the level:
  - without the semicolon rule, a rater may accept a level when only some of its joined requirements are met;
  - without the OR rule, a rater may treat alternatives as joint requirements.

  At a level above 0 these two make a score above 0 easier and harder, respectively. At level 0, where some
  criteria use the same operators (P1, P3 and P4 level 0 in v1.0), the directions reverse. Their effects may
  therefore cancel. A null result cannot separate them, and a net change is credited to
  removing both operator rules, not to either one. No analysis by criterion is made.
- **How it is reported.** It is exploratory: no reading is applied, and no correction is made for the number
  of measures. Every measure is reported with its intervals, whatever its direction, in neutral sentences
  (REPORTING_RULES_REPLICATION.md §4). No interval is described as showing an effect.

### Partial runs and eligibility

- **Fewer than 10 papers:** if fewer than 10 papers have at least one execution complete in both confirmatory
  arms, the results are descriptive only. The three-way and equivalence readings are not used.
- **Fewer than 10 papers without hazard detectors:** the hazard sensitivity reading is not applied; its numbers
  are reported descriptively.
- **Ineligible papers:** a paper found ineligible after the run is not removed; it is noted.

## Stopping rules (fixed now; no decision is taken after seeing results)

- **Retried first:** every provider 5xx, and every 429 that carries no quota or billing code and no credit word
  (as above), is retried by
  the transport (three attempts), then re-requested up to three times (each again with three attempts). A
  quota or billing error is never retried.
- **Never a stop:** a recorded content outcome. This means a reply that could not be read, was incomplete, or
  failed the format or evidence checks after its re-requests, a paper whose input was flagged as unusable at
  the freeze, and a request in flight at an earlier interruption. These are kept as failures of their panels, and the run carries on.
  - A provider failure inside the format-recovery or quotation-correction turn ends as a format or evidence
    failure of that request. A credit error there therefore stops the run at that provider's next request.
- **The runner stops** on the first request of a launch that ends in one of these. It prints the cause, the
  HTTP status and the provider's error type, code and message (`final_phase.stop_cause`):
  1. **Provider outage** (`cause: provider outage`): a 5xx or 429 that outlasted every retry and re-request.
     The request is recorded as a failure.
  2. **Network or transport** (`cause: network or transport`): a connection error or timeout, with no HTTP
     status, that outlasted every retry and re-request.
  3. **Credit, billing or configuration** (`cause: credit, billing or configuration`): a quota or billing code,
     or another non-200 status, or a provider error whose text mentions balance, credit, quota, billing,
     payment, arrears or insufficient (as words anywhere in the message). **Whatever the cause says,** a stop whose provider error mentions
     any of these counts as a credit stop.
  4. **Model identity change** (`cause: model identity change`). A retired model that returns an HTTP 404
     appears as cause 3 instead. Both are final stops.
  5. **Runner refusal** (`cause: runner refusal`, or any other runner error or traceback):
     - a failure before any provider reply (credential, admission, code drift), including one after an earlier
       failed attempt;
     - a 200 reply the runner refuses: usage beyond the reservation, an echoed secret, a missing model
       identity, or an unreadable provider envelope;
     - a changed frozen request, an input hash mismatch, or a final `"stopped"` result.
  6. **Local interruption:** sleep, power loss, or the process ended by something other than the operator,
     with none of 1–5 recorded. A connection failure, including the loss of the machine's own network, is
     always cause 2, never this case. **A deliberate stop by the operator is a final stop.**
- **Resumes are mechanical, never a choice,** and only after a provider outage (1), a network or transport
  stop (2) or a local interruption (6):
  - **Automatic, after an outage or a network stop.** The run chain (`scripts/repl_chain.sh`, hashed in the
    release's `CODE_HASHES.json`) waits, then relaunches itself.
    - The wait is 5 × 2^k minutes, where k is the number of automatic resumes so far: 5, 10, 20, 40 … minutes.
      The waits double, so they span the 72 hours (at most nine fit), also for an HTTP outage during which
      connections still open.
    - After that wait it continues until all three providers accept a connection again (checked every five
      minutes, with a TCP connection only and no request sent).
    - It does this after every such stop, up to 10 times per launch of the chain.
    - The 72 hours are counted in real time from the first such stop of the whole run. That time is kept in a
      file and is never reset, also across a manual relaunch. Once 72 hours have passed, the stop is final,
      whether that point falls during a wait or at a later outage or network stop. The clock is checked every
      five minutes, so this final stop can come up to five minutes after the 72 hours. A stop after the 10th
      automatic resume is also final.
    - These resumes act on the printed cause alone, re-send nothing and see no result, so they are not limited
      to one.
    - **Final stops are recorded.** Every final stop is marked by a marker file, and the chain refuses to start
      while the marker exists. The chain writes it on its own final stops. The operator writes it, with a dated
      status line, for a deliberate stop, a second local interruption and a missed 72-hour manual resume
      (`goal-b/01_RUN.md` §7). Every launch's logs are kept, never overwritten.
  - **One manual resume, after a local interruption.** The operator relaunches as soon as the interruption is
    found, with no other condition. An interruption during a wait (after an outage or network stop) counts
    as a local interruption: the relaunched chain goes back to waiting. Monitoring before that shows only total counts, never counts by run or
    arm. If this resume has not happened within 72 hours, the stop becomes final and the missed resume is
    reported as a deviation.
  - **In every resume:** the same command, unchanged. Requests already dispositioned, including an outage's
    failed request, are skipped and never re-sent. A request in flight at an interruption is not re-sent
    either: the runner finds its reservation without a reply, records it as a failure ("Unknown interrupted
    provider attempt"), and carries on.
  - **Resumes are part of this procedure, not deviations.** Each stop and resume is reported with its date and
    cause.
  - **The result** is the comparison at the end of the run, or at its final stop. No comparison is computed at
    any earlier stop.
- **Final stops:**
  - a credit, billing or configuration stop (3), a model identity change (4) or a runner refusal (5);
  - a local interruption after the manual resume has been used;
  - an outage or network stop after the 10th automatic resume, or more than 72 hours after the first such
    stop;
  - any stop whose cause is unclear.
  - There is no top-up during the run.
- **After a final stop:** each comparison uses the paper-executions complete in its own two arms (above), and
  the stop is reported with its cause and the request count at which it occurred.
- **No result before the run ends:** no comparison is computed before the run has finished or stopped finally.
  Monitoring uses only log counts and spend. No resume or relaunch happens after any result of this run has
  been computed.
- **Not repeated:** the run is not repeated, and no paper is re-rated because of its result. Failed or partial
  requests are kept; none is re-sent because of what it contained.

## Cost and launch condition

Estimate from the completed v2.0 run's charge per R0 request (all attempts included), × 114 requests per arm
and provider, plus the smoke run:

| Provider | Estimate (US$) | Minimum balance at launch = estimate × 1.3 (US$) |
|---|---:|---:|
| Anthropic | 28.78 | 37.42 |
| OpenAI | 17.54 | 22.80 |
| Z.AI | 25.59 | 33.27 |
| Total | 71.91 | 93.48 |

The launch is refused if any provider's balance, as reported by Gabriel from its console with automatic
top-ups off, is below its minimum. These minimums (called "caps" in the working files) are launch conditions,
not limits during the run. Provider credit is the only limit during the run, and a credit error is a final
stop.

## Analysis

- **Script:** `scripts/repl_report.py`, at the hash listed in the release (`CODE_HASHES.json`), run on a
  `.backup` copy of the ledger.
- **Tested in advance:** before any replication data existed, it was tested on synthetic ledgers. On the
  completed v2.0 ledger, with its arms mapped in, it reproduced the published numbers exactly: +7.2 [+0.2,
  +13.8]; complete and agreeing +2.6 [−4.4, +9.7]; Table S8; permutation p; BCa.
- **Outputs:** it writes REPL_RUN.json once, and never rewrites it.
- **A change to the script after publication** is a dated deviation, reported with both results.
- **Reporting:** the sentences that report each outcome are fixed in REPORTING_RULES_REPLICATION.md,
  published with this document.

## What this test does not change

- **The v2.0 test:** its results, readings and fixed sentences are unchanged.
- **The rubric:** v1.2 revision 3 is final. Disagreements found here are reported as residual and left to
  future work, with no new wording.
- **The published files:** rubric v1.0, rubric v1.2 revision 3, `HANDBOOK_H5.txt` and
  `HANDBOOK_EVAL_ORIGINAL.txt` are not edited.

## Deviations

Every departure from this document after publication is dated and reported with the results.
