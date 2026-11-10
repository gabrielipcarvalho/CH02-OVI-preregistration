# Pre-registration: OVI rubric v1.2 revision 3 against the published v1.0 on papers published after the SLR

**Status: APPROVED by Gabriel, 10 November 2026, and published with its stage 2 amendment as v2.0 of
`gabrielipcarvalho/CH02-OVI-preregistration`.** Drafted 1 November 2026. Provenance:
agent:claude-opus-5-5. Paper selection follows [SEARCH_PROTOCOL.md](SEARCH_PROTOCOL.md).

**Publication in two stages, both before the first rated request:**
- **Stage 1:** this document, before the search is run. It is released as v2.0 of
  `gabrielipcarvalho/CH02-OVI-preregistration`. The push is Gabriel's.
- **Stage 2:** an amendment before freezing that adds the screened paper list, the hazard-detector
  flags and the input hashes. Nothing else in this document may change in it.

## Question

Does the refined rubric (v1.2 revision 3 with procedure H5) let three independent AI raters resolve more
panels than the published rubric (v1.0) on papers that no version of the rubric, handbook or pipeline
has seen?

- **What it adds:**
  - CORPUS3B measured this on the papers v1.2 was refined from (+16.7 points [11.0, 22.9]).
  - CORPUS2 measured v1.1 on unseen papers (+8.6 [0.6, 17.0]), but that result depends on the
    hazard-detector papers (`results/HAZARD_SENSITIVITY.md`).
- **The question here:** whether the final text transfers.

## Arms (the only difference is the rubric and its procedure)

| Arm | Rubric | Procedure |
|---|---|---|
| POSTSLR_V12 | `rubric/rubric_v1_2_r3.yaml` | `HANDBOOK_H5.txt` |
| POSTSLR_V10 | the published v1.0 (`rubric/rubric.yaml`) | `HANDBOOK_EVAL_ORIGINAL.txt` |

**Fixed in both arms, as in CORPUS3B unless stated:**
- **Raters:**
  - gpt-6.1-sol, reasoning effort low;
  - glm-5.3, thinking on, reasoning effort high, JSON mode;
  - claude-sonnet-5-5, effort medium.
  - Each rater gets a 16,000-token output cap and the final check v2.
- **Inputs:** md-v1 Markdown with frozen figure descriptions, under a new manifest for these papers.
- **Pipeline:**
  - validator md-page-v1.3, with the adjacent-page rule;
  - quote-correction-v1;
  - glm-repair-v2;
  - discussion-v1.
- **Re-request policy: `unreadable-resample-v4`** (DEC-0011), new for this run. A reply with no readable
  pillar, an incomplete reply, or a provider failure is re-requested up to three times, unchanged.
- **The rest of the procedure:**
  - each rater receives only the paper, the rubric and the procedure;
  - no spending limits other than provider credit.
- **Model identity:** if a pinned model is retired or returns a different identity, the run stops and
  the stop is reported. No model is substituted.

## Papers

- **The set:** every paper that passes the screening in SEARCH_PROTOCOL.md, listed in the stage 2
  amendment. There is no target number.
- **If fewer than 10 papers are eligible:** the run still goes ahead, but the result is reported as
  descriptive only. The "transfers" reading below is not used.
- **Exposure:** none of these papers has been opened for scoring, used to write any rubric text, or seen
  by any rater before the run. Anything that breaks this, such as a paper looked at during conversion
  checks, is disclosed per paper.

## Design

- **Executions:** 2 per arm.
- **Order:** one schedule interleaving both arms, in a seeded random order (seed
  `ch2-postslr-20261101`), unlike CORPUS3B.
- **Discussion:** in both arms, per execution, after the independent round (R0) of both arms is
  complete. Contested panels only.
- **First call:** D0_V4 on the fictional fixture must pass before the first real request.

## Measures (as declared for CORPUS3B, `CORPUS_RUN_MEASURES.md`)

A **panel** is one paper × one pillar × one execution. A panel is **resolved** when the three raters give
the same score, each backed by a verified quotation or the absence marker, or all three judge the pillar
not applicable.

- **Primary:** the paired difference in the proportion of resolved panels in R0, v1.2 r3 minus v1.0,
  with executions pooled.
  - **Interval:** a 95% interval from a paper bootstrap (10,000 resamples, seed `ch2-postslr-20261101`).
  - **Also reported:** the discordant pairs in each direction.
- **Secondary, with the same interval:**
  - complete and agreeing panels in R0;
  - resolved panels after discussion. This is a dependent reconciliation stage and never replaces R0.
- **Sensitivity:** the primary and secondary measures without the hazard-detector papers flagged at
  screening (DEC-0010's definition).
- **Descriptive only:**
  - **Detail:** per pillar; papers agreed out of scope; failures by category; how often the correction
    turn, each re-request and the adjacent-page rule fired.
  - **Coverage:** before re-requests (from the first reply alone) and after them.
  - **Agreement beyond 0:** agreement on panels where at least one rater scored above 0, because most
    scores are 0 and that makes agreement easy.
  - **OVI-Gate** of every agreed profile.
  - **Stability:** repeat stability across the two executions.
  - **Effect sizes:** this run's primary difference set beside CORPUS3B's and CORPUS2's.

## Reading (fixed now; the prose is chosen after the results)

1. **Transfers:** the primary interval's lower bound is above 0. v1.2 revision 3 resolves more panels
   than v1.0 on unseen papers.
2. **Not detected:** the interval includes 0. No difference is detected on unseen papers. CORPUS3B's gain
   is then reported as specific to the papers the rubric was refined from.
3. **Reverses:** the upper bound is below 0. v1.0 resolves more panels on unseen papers.

## What this run does not change

- **The rubric:** v1.2 revision 3 is final (DEC-0009, ruling 11). Disagreements found here are reported
  as residual and left to future work, with no new wording.
- **No reruns:** the run is not repeated, and no paper is re-rated because of its result.
- **Failed or partial requests:** kept, never replaced. No request is re-sent because of what it
  contained.

## Stopping

- **When the run stops:** a provider billing or credit error, a model identity change, or a dispatcher
  error.
- **Then:** the comparison uses only paper-executions complete in both arms, and the stop is reported.
- **Cost estimate:** about US$25 for 20 papers (SEARCH_PROTOCOL.md). This is an estimate, not a limit.

## Deviations

Every deviation after stage 1 is dated and reported with the results.

## Decisions for Gabriel before stage 1 (settled)

Settled as follows; the late timing is dated in the stage 2 amendment, under Deviations:
- **Who screened:** the analyst, with Gabriel checking every decision ("You screen, I check").
- **Searches:** the analyst ran the arXiv, PubMed and supplementary OpenAlex searches.
- **Approval and publication:** approved on 10 Nov 2026 ("Proceed with 1 and 2").

The questions as they were asked:


1. Who screens: Gabriel (recommended), or the analyst with Gabriel checking.
2. Whether the analyst runs the arXiv and PubMed searches.
3. Approval of this document, and the push of the v2.0 release.
