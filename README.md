# CH02 pre-registration: held-out evaluation of a refined LLM application protocol for the OVI rubric

This repository time-stamps the frozen plan for the held-out evaluation in Chapter 2 of Gabriel Carvalho's
PhD (Griffith University). The study is an AI-only, evidence-verified application of the published
four-pillar Operational Viability Index (IEEE Access, doi:10.1109/ACCESS.2026.3701060) to
drowning-detection research.

**Release `v1.0` was published before the first held-out request was sent.** GitHub records the release
date on its own servers.

| File | Content |
|---|---|
| `PREREGISTRATION.md` | The question, the two arms, the 15 held-out papers, outcomes, the analysis plan and stopping rules |
| `CH02_prereg_0602c83.zip` | The exact files from the research repository at commit `0602c8399c02387c61d7281e5c3ce6c3ec9d4b28` (see the list below) |
| `SHA256SUMS.txt` | SHA-256 of the two files above, plus the source commit |

The zip contains:
- the frozen handbooks for the original and refined arms;
- the design and its amendments;
- the development-loop results;
- the validator qualification;
- the input manifest, as hashes only;
- the runner and validator code;
- the rubric, protocol and schema.

The research repository is private. No paper text, figure image or provider data is included here.
Results will be reported against this plan, and every deviation will be dated.

## v2.0: the post-SLR evaluation (stages 1 and 2)

**Release `v2.0` time-stamps the plan for testing the final refined rubric (v1.2 revision 3) against the
published v1.0 on 57 papers published after the SLR's search.** No rater has seen these papers. The
release was published before the freeze and before the first rated request.

**It was published late.** Stage 1 was meant to be public before the search, and it was not. The
amendment dates this and every other deviation.

**Correction, 25 November 2026:** [`CORRECTION_v2.0_2026-11-25.md`](CORRECTION_v2.0_2026-11-25.md) corrects
the screening disclosure, records the stopped and resumed run, and notes that the replication (v3.0, amended
by v3.1) is now the primary result on transfer.

| File | Content |
|---|---|
| `PREREGISTRATION_POSTSLR.md` | Stage 1: the question, the two arms, the design, the measures and the reading |
| `PREREGISTRATION_POSTSLR_STAGE2.md` | Stage 2 amendment: the 57 screened papers, the hazard-detector flags, the input hashes, the exposure disclosure and the deviations |
| `CH02_postslr_prereg_7cd71da.zip` | The exact files from the research repository at commit `7cd71da1d0342b095e52d8a200544158c0a31e8a` |
| `SHA256SUMS.txt` | SHA-256 of the v2.0 files, under its own heading, below the v1.0 entries |

The zip contains:
- the search protocol, the search, screening and full-text logs, and the conversion review;
- the input manifests, as hashes only;
- both rubrics, both handbooks and the protocol;
- the measures and decisions DEC-0009 to DEC-0011;
- the search, screening, conversion and figure-description code.

No paper text, figure image, figure description or screening table is included.

## v3.0: replication and operator-rule ablation

**Release `v3.0` time-stamps the plan for a pre-registered replication of the v2.0 comparison (rubric v1.2
revision 3 against the published v1.0) on the same 57 papers, run from the start.** A third, exploratory arm
applies v1.0 with a procedure that omits two sentences: the one on semicolon-separated requirements and the
one on an explicit OR. The three arms are interleaved. The release was published before the freeze and
before the first rated request.

The v3.0 files are in the `v3.0/` folder, which has its own README and `SHA256SUMS.txt`. They are also listed
under their own heading in the root `SHA256SUMS.txt`, below the v2.0 entries.

| File | Content |
|---|---|
| `v3.0/PREREGISTRATION_REPLICATION.md` | The questions, the three arms, the measures, the readings, the equivalence bound, the stopping rules and the cost condition |
| `v3.0/REPORTING_RULES_REPLICATION.md` | The sentences that report each possible outcome, fixed before the run |
| `v3.0/HANDBOOK_EVAL_ORIGINAL_NOCONJ.txt` | The ablation arm's procedure |
| `v3.0/CH02_prereg_v3_81895c8.zip` | The exact files from the research repository at commit `81895c8e15218d62a7e73e1c9b526356ef8ea429` |
| `v3.0/CODE_HASHES.json` | SHA-256 of the runner and analysis files |

No paper text, figure image, quotation or provider data is included.

## v3.1: amendment to v3.0 (which result leads)

**Release `v3.1` amends v3.0 before any result of the replication was computed.** It makes the replication
the article's primary result on transfer and reports the original test (v2.0), whose run stopped and was
resumed, as the earlier, procedurally compromised test, whatever the replication shows. It changes the role
and order of the reporting sentences only: the arms, measures, readings and stopping rules of v3.0 are
unchanged.

| File | Content |
|---|---|
| `v3.1/AMENDMENT_V3_1.md` | The amendment: the rule, the reporting changes for every outcome, and what does not change |
| `v3.1/SHA256SUMS.txt` | SHA-256 of the amendment |
