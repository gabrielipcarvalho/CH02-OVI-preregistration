# Pre-registration: held-out evaluation of a refined LLM application protocol for the OVI rubric

**Status: APPROVED by Gabriel on 28 October 2026.** It is binding from the commit that adds it, and is
publicly time-stamped before the first held-out request. Authored with Claude (Opus 5.5).

## Question

Does an application handbook refined on development papers increase the share of usable,
consistent three-LLM judgments on papers it has never seen, compared with the original handbook,
when everything else is held fixed?

## Arms (the only difference between them is the handbook text)

| Arm | Handbook | What it contains |
|---|---|---|
| EVAL_ORIGINAL | `HANDBOOK_EVAL_ORIGINAL.txt` (sha256 `b1f05abc…`) | The cycle-0 handbook (Larry's D1 scope, D2 conjunction, D3 consent) plus one format line (exactly four cells). |
| EVAL_REFINED | `HANDBOOK_C3.txt` (sha256 `4a2d84bf…`) | The same, plus every clarification from cycles 1–3 (B–F, J, K–O). |

The four-cell format line is in both arms. It is a technical fix, so leaving it out of the original
arm would confound the comparison with a known format failure.

**Fixed in both arms:**
- The published rubric, unchanged.
- The AI-only rater protocol.
- md-v1 inputs with frozen figure descriptions (`MARKDOWN_MANIFEST.json`, sha256 `d9efa88e…`).
- Validator md-page-v1.1, qualified 72/72 (`QUALIFICATION_MD_V1_1.json`, sha256 `8ceee054…`).
- Models and settings:
  - gpt-6.1-sol, reasoning effort low;
  - glm-5.3, thinking on, reasoning effort low, JSON mode;
  - claude-sonnet-5-5, effort medium.
- A 16,000-token output cap.
- Retries: at most 2 transport retries and 1 format recovery.
- R0 only, independent and fresh context, no deliberation.

## Papers

Fifteen held-out primaries, selected on 28 October by SHA-256 order of
`"ch2-final-heldout-20261028-v1:<id>"` from the 41 primaries that have a text layer, no recent direct
use and are not in the October evaluation set:
**14, 17, 18, 25, 27, 28, 31, 40, 47, 51, 59, 71, 72, 74, 79.**

- None was used in refinement or opened for scoring before dispatch.
- *Disclosed exposure:* the August alpha raters saw them. Short extraction fragments of paper 28 were
  viewed during conversion QA. Their figures were described automatically, and none was in the
  spot-check sample.

## Design

- **Volume:** 2 arms × 15 papers × 3 models × 3 fresh executions = 270 requests, 1,080 requested
  judgments and 180 requested panels per arm.
- **Order:** arms are interleaved in a seeded random order.
- **First call:** a D0 smoke run must pass before the first held-out call.

## Outcomes

- **Primary.** Complete and agreeing panels divided by requested panels, per arm. A panel is paper ×
  pillar × execution. Complete means three validated numeric scores; agreeing means identical scores.
- **Secondary:**
  - coverage;
  - conditional agreement;
  - resolved panels (a post-hoc measure from development, labelled as such);
  - numeric, null and failure counts by model and failure category;
  - within-model repeat stability across the three executions;
  - OVI-Gate distribution of complete profiles;
  - truncations, attempts and cost.
- **Sensitivity.** All outcomes are reported with and without hazard-detector papers, because
  clarification D still awaits Larry's confirmation.

## Analysis and interpretation

- Results are descriptive, with every numerator and denominator reported. The paired difference
  (refined − original) in the primary outcome is reported overall, per pillar and per paper.
- No significance tests. Panels and executions are dependent, and 15 papers give no
  precision-planned sample.
- The outcome version to report is fixed in advance in `CONTRIBUTION.md` §"Pre-written outcome
  versions": improves, does not improve, or mixed. The prose is chosen only after the results.

## Stopping and spending

- **Expected cost:** about US$17, based on development request sizes.
- **Stop conditions:** a provider credit or billing error, a model identity change, or final-phase
  spend of US$100. The phase reserves US$25 for this evaluation.
- **Data handling:** failed or partial requests are kept, never replaced, and no request is retried
  because of its scientific content.
- **Interruptions:** any interruption and resumption is disclosed with dates.

## Deviations

Every deviation from this document after freezing is dated and reported. The development loop's
deviations (Amendments 1 and 2, the analyst's extension of change I, and the delegated rulings K–O)
are recorded in LOOP_DESIGN.md and the CHANGESET files.
