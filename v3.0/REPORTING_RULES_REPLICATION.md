# Reporting rules for the replication (v3.0), fixed before any request

Provenance: agent:claude-opus-5-5, 18 November 2026 (Goal A; revised after the Goal A design review). This file
is published with [PREREGISTRATION_REPLICATION.md](PREREGISTRATION_REPLICATION.md) as v3.0, before the freeze
and the first rated request. For every outcome, it fixes the sentences that report the replication in the
article. It plays the role OUTCOME_RULES.md and RESUME_REPORTING_RULES.md played for v2.0, but it is written
before the run rather than during it, and it keeps OUTCOME_RULES' qualifications of the headline in §5.5,
with one declared departure: B's hazard-dependence sentence needs the hazard-free upper bound to lie below the
full estimate, where OUTCOME_RULES §2 needed only a different reading. The
abstract carries the kind of agreement and the hazard-dependence clause; the neutral hazard sentence (B's
second row) and the complete-and-agreeing difference go to §5.5 only, for want of space. The abstract's
level-0 and above-0 differences add up to the complete-and-agreeing difference, and with the not-applicable
difference to the resolved difference, so the abstract states the split OUTCOME_RULES asks for.

## Notation

Numbers enter only through the macros that `scripts/repl_report.py` writes (`repl_numbers.tex`), never typed by
hand. In the sentences below:
- `D [L, U]` is `\replResolvedDiff{} [\replResolvedLow{}, \replResolvedHigh{}]`;
- `[L90, U90]` is `[\replResolvedLowNinety{}, \replResolvedHighNinety{}]`;
- `CA` is `\replCADiff{} [\replCALow{}, \replCAHigh{}]`;
- `KZ`, `KA` and `KN` are `\replKindZeroDiff{}`, `\replKindAboveZeroDiff{}` and `\replKindNADiff{}`, each
  followed by its interval (`\replKindZeroLow{}`, `\replKindZeroHigh{}`, and likewise);
- `Δ` is `\replBound{}` (the equivalence bound, 10 points);
- `n` is `\replPapersCompared{}`.

## 1. What stays as it is

- **The v2.0 test** is reported exactly as now:
  - the stopped comparison is its pre-registered result: *not detected*, −2.4 [−14.3, +8.1];
  - the completed comparison is a declared deviation: +7.2 [+0.2, +13.8], *transfers* when the rule is
    applied descriptively;
  - their fixed sentences (OUTCOME_RULES.md §2; RESUME_REPORTING_RULES.md) are not edited.
- **The replication** is reported as a separate pre-registered test of the same question, named "the
  replication" in the text, with its own reading.
- **The ablation** is reported as exploratory, in its own sentences, and never in the abstract's result
  sentence.

## 2. The confirmatory report (§5.5 and the conclusion; the abstract uses the short form fixed in §3)

It is built from four parts, always in this order: **A**, then **B**, then **C**, then **D**. Each part's
sentence is chosen by the readings in REPL_RUN.json. No other wording is used.

### A. The result: three-way reading × equivalence reading (`within the bound`, `not shown`, `beyond the bound`)

| Reading | Equivalence | Sentence A |
|---|---|---|
| transfers | not shown | "In a pre-registered replication on the same papers, v1.2 revision 3 resolved more panels than v1.0 (D points [L, U]); the 90% interval does not exclude a gain of Δ points or more." |
| transfers | within the bound | "In a pre-registered replication on the same papers, v1.2 revision 3 resolved more panels than v1.0, by less than Δ points: gains of Δ points or more are excluded by the 90% interval (D [L, U]; 90% interval [L90, U90])." |
| transfers | beyond the bound | "In a pre-registered replication on the same papers, v1.2 revision 3 resolved more panels than v1.0, by Δ points or more (D [L, U]; 90% interval [L90, U90])." |
| not detected | within the bound | "In a pre-registered replication on the same papers, no difference was detected, and differences of Δ points or more in either direction are excluded by the 90% interval (D [L, U]; 90% interval [L90, U90])." |
| not detected | not shown | "In a pre-registered replication on the same papers, no difference was detected (D [L, U]); the 90% interval does not exclude a difference of Δ points." |
| reverses | within the bound | "In a pre-registered replication on the same papers, v1.0 resolved more panels than v1.2 revision 3, by less than Δ points (D [L, U]; 90% interval [L90, U90])." |
| reverses | not shown | "In a pre-registered replication on the same papers, v1.0 resolved more panels than v1.2 revision 3 (D [L, U])." |
| reverses | beyond the bound | "In a pre-registered replication on the same papers, v1.0 resolved more panels than v1.2 revision 3, by Δ points or more (D [L, U]; 90% interval [L90, U90])." |
| not detected | beyond the bound | "In a pre-registered replication on the same papers, the 95% interval included zero (D [L, U]) while the 90% interval lay beyond Δ points ([L90, U90]); the result is reported as inconclusive." |

### B. The qualification (in the manner of OUTCOME_RULES §2 for v2.0)

`H [HL, HU]` is the result without the hazard-detector papers (`\replNoHazardDiff{}` [`\replNoHazardLow{}`,
`\replNoHazardHigh{}`]).

- **If the reading is *transfers*,** first one hazard row (at most one applies), then exactly one CA row. The
  CA bias clause "(complete and agreeing panels exclude agreed not applicable, which v1.2 revision 3 can
  produce more of by design)" follows every CA sentence, here and in D1:

  | Condition | Sentence B |
  |---|---|
  | the reading without hazard detectors was applied, is not *transfers*, and HU lies below D | "The gain depends on the hazard-detector papers: without them the difference is H [HL, HU], whose upper bound lies below the full estimate." |
  | the reading without hazard detectors was applied, is not *transfers*, and HU is at or above D | "Without the hazard-detector papers the difference is H [HL, HU] (*[sensitivity reading]*)." |
  | the reading without hazard detectors was not applied (fewer than 10 such papers) | "Too few papers without hazard detectors were compared to tell whether the gain depends on them." |
  | the CA interval lies above 0 | "The gain includes more identical scores (complete and agreeing: CA)." |
  | the CA interval includes 0 | "Complete and agreeing panels did not detectably change (CA); the resolved-panel difference splits as agreement at level 0 KZ, agreement above 0 KA and agreed not applicable KN." |
  | the CA interval lies below 0 | "Complete and agreeing panels fell (CA); the resolved-panel difference splits as agreement at level 0 KZ, agreement above 0 KA and agreed not applicable KN." |

- **If the reading is *not detected*,** one row, from the equivalence reading and U:

  | Condition | Sentence B |
  |---|---|
  | within the bound | "The 90% interval excludes a gain the size of the exposed-corpus gain (+16.7, from a different paper mix and re-request policy)." |
  | not shown, and U is at or above +16.7 | "The interval does not exclude a gain the size of the exposed-corpus gain (+16.7)." |
  | not shown, and Δ ≤ U < +16.7 | "The interval excludes a gain the size of the exposed-corpus gain (+16.7) but not one of Δ points." |
  | not shown, and U < Δ | "The interval excludes gains of Δ points or more, but the 90% interval does not exclude a loss of Δ points ([L90, U90])." |
  | beyond the bound | "No conclusion about the exposed-corpus gain is drawn from an inconclusive result." |

  U, HU and D are compared as the 4-decimal values in REPL_RUN.json (+16.7 is 0.167; Δ is 0.10).

- **If the reading is *reverses*:** "The refined rubric is not recommended over v1.0 on this evidence (the
  release decision is the authors')."

### C. The relation to the original test (both of its comparisons)

| Reading (and equivalence) | Sentence C |
|---|---|
| transfers | "This differs in reading from the original test's pre-registered comparison, which detected no difference, and agrees in reading with its completed comparison, a declared deviation." |
| not detected, within the bound or not shown | "Like the original test's pre-registered comparison, it detected no difference; the original test's completed comparison, a declared deviation, gave *transfers*." |
| not detected, beyond the bound | "It is reported beside both comparisons of the original test, without a reading." |
| reverses | "This differs in reading from both comparisons of the original test." |

### D. Always, in every case

1. **Kind of agreement and complete-and-agreeing** (with equal prominence to A, as OUTCOME_RULES requires):
   "Agreement at level 0 changed by KZ, agreement above 0 by KA and agreed not applicable by KN; complete and
   agreeing panels changed by CA (complete and agreeing panels exclude agreed not applicable, which v1.2
   revision 3 can produce more of by design)."
   - If B already gave the split, D1 is left out.
2. **Score and scope agreement** (§5.5 only): "On panels all three raters scored in both arms, identical
   scores changed by `\replScoresDiff{}` [`\replScoresLow{}`, `\replScoresHigh{}`] (without P3:
   `\replScoresNoPThreeDiff{}` [`\replScoresNoPThreeLow{}`, `\replScoresNoPThreeHigh{}`]); scope agreement per
   panel changed by `\replScopePanelDiff{}` [`\replScopePanelLow{}`, `\replScopePanelHigh{}`]. Scope agreement
   favours v1.2 revision 3 by design, because H5 asks for one scope decision per paper. Identical scores on
   fully scored panels include agreement at level 0, which is easy (in v2.0 most such panels were at 0).
   Panels with a failed judgment, which count as unresolved, changed by `\replFailedDiff{}`
   [`\replFailedLow{}`, `\replFailedHigh{}`]."
3. **Hazard sensitivity** (§5.5 only, when B did not already give it): "Without the hazard-detector papers
   the difference is H [HL, HU] (*[sensitivity reading]*)."
   - If fewer than 10 such papers were compared, use instead: "Too few papers without hazard detectors were
     compared to apply the reading (H [HL, HU], descriptive)."
4. **Exposure** (§5.5 only): "The replication used the papers of the original test, so it tests the procedure
   again rather than new papers."
5. **A final stop,** if there was one: "The replication stopped finally after `\replRequestsDispositioned{}`
   of 1,026 requests (cause: *[cause]*); the comparison uses n papers with at least one execution complete in
   both arms."
   - *[cause]* is the runner's `cause:` text quoted verbatim from `repl-r0.err`.
   - When there is no such line, *[cause]* is the fixed phrase for the case:
     - "a local interruption" (process ended by something other than the operator);
     - "a deliberate stop by the operator";
     - "a local interruption, not resumed within 72 hours";
     - "72 hours after the first outage or network stop" (the chain's `STOP` line), followed by the last cause
       quoted from the last `repl-r0-launchN.err`;
     - "an outage or network stop after the 10th automatic resume" (the chain's `STOP` line), followed by
       the cause quoted from `repl-r0.err`;
     - "a budget stop" (a `"stopped"` result in `repl-r0.log`);
     - "a runner error" (any other traceback);
     - "an unclear cause" (anything else, with the `.err` file kept in the supplement's materials).
   - It goes in §5.5, and as the clause "(stopped after `\replRequestsDispositioned{}` of 1,026 requests)"
     after A in the abstract.
6. **Resumes,** if there were any (§5.5 and the supplement's list of dates): "The run was stopped and resumed
   *[k]* times (causes: *[the causes, as in D5]*), as the pre-registration requires." *k* is the number of
   `RESUME` lines in `repl-chain.status` plus the manual relaunch, if any, quoted from those files.
7. **The pre-registered sensitivity analyses** (§5.5 and the supplement), always (when `\replPermP{}` prints
   0.000, write "p < 0.001" instead of "p = 0.000"): "A paper-level permutation test gave p = `\replPermP{}`, and a bias-corrected and accelerated interval gave `\replBcaLow{}` to
   `\replBcaHigh{}`." Then, if they disagree with the three-way reading, one of these is added. Whether p ≥ 0.05
   is judged on the unrounded `permutation_p_two_sided` in REPL_RUN.json, and the BCa bounds on the JSON values:
   - transfers, with the BCa interval reaching 0 or below, or p ≥ 0.05: "These sensitivity analyses do not all
     support the reading.";
   - reverses, with the BCa interval reaching 0 or above, or p ≥ 0.05: the same sentence;
   - not detected, with the BCa interval excluding 0 or p < 0.05: "These sensitivity analyses do not all agree
     with the reading."

**If fewer than 10 papers are compared,** this replaces A to D: "The pre-registered replication stopped finally
after `\replRequestsDispositioned{}` of 1,026 requests (cause: *[quoted verbatim]*), with n papers compared;
its results are reported descriptively (D points [L, U]) and no reading is applied."
- If no paper was compared, the sentence ends at "n papers compared", with no numbers.
- Conclusion: this sentence alone.
- Highlight: "Pre-registered replication stopped early; reported descriptively".
- Figure 2: the row is drawn hollow and labelled "replication (stopped; descriptive)".
- There is no C sentence.

## 3. Abstract, highlights, conclusion, figure

- **Abstract** (fixed now, because the current abstract is already at 250 words; `tests/test_repl_run.py`
  checks that the longest case below fits):
  - **What is added: one sentence, after the v2.0 sentence that ends "on \prrPapersCompared{} papers."** It is
    built from these pieces, in this order, then a full stop:
    1. "A pre-registered replication";
    2. only after a final stop: "(stopped after `\replRequestsDispositioned{}` of 1,026 requests)";
    3. by reading: transfers "on the same papers found the revision resolved more panels"; not detected "on
       the same papers detected no difference"; reverses "on the same papers found the revision resolved fewer
       panels";
    4. "(D points, L to U)";
    5. by equivalence: within the bound ", excluding Δ-point differences (90% interval)"; beyond the bound
       ", by Δ points or more (90% interval)" (or "; the result is inconclusive" when not detected); not
       shown nothing. The "(90% interval)" label is part of the piece, because piece 4 gives the 95% interval;
    6. the kind of agreement, always (OUTCOME_RULES §2's equal prominence): "(points: level 0 KZ, above 0 KA,
       not applicable KN)", with the point differences only (`\replKindZeroDiff{}`, `\replKindAboveZeroDiff{}`,
       `\replKindNADiff{}`; their intervals are in §5.5);
    7. only when B's hazard-dependence row applies: "; the gain depended on the hazard-detector papers";
    8. only when D7's disagreement sentence applies: "; not all sensitivity analyses agreed". It is never cut.
  - **Fewer than 10 papers compared:** the sentence is instead "A pre-registered replication on the same papers
    stopped early with n papers compared and is reported descriptively."
  - **What is not added.** B's other rows, C and the rest of D go to §5.5.
  - **What stays.** The v2.0 sentences required by OUTCOME_RULES §2 and RESUME_REPORTING_RULES stay
    unchanged.
  - **The closing sentence.** "Evidence of transfer is inconclusive;" is replaced, by the replication's
    reading, with the first that applies:
    - D7's disagreement sentence applies (any reading): "Evidence of transfer remains inconclusive;";
    - transfers: "Evidence of transfer now comes from one replication;";
    - not detected and within the bound: "No transfer of the exposed-corpus gain was found;";
    - not detected otherwise: "Evidence of transfer remains inconclusive;";
    - fewer than 10 papers compared: "Evidence of transfer remains inconclusive;";
    - reverses: "The refinement did not transfer;".
    - The rest of the sentence ("evaluations should report failed judgments and test refinements on unseen
      papers.") stays.
  - **Cuts to keep 250 words,** made in this order and only as far as needed:
    1. delete "Our system records both.";
    2. delete ", and failures are counted";
    3. delete "The study measures consistency and checked evidence, not accuracy against expert judgment."
       (it stays in §1);
    4. replace "The gap came from mechanical failures, then scope disputes and unclear wording; the latter led
       to 19 rubric changes." with "Unclear wording led to 19 rubric changes.";
    5. delete "(paper-pillars)";
    6. replace "LLM systems that apply appraisal rubrics are usually judged by agreement, which hides judgments
       they fail to produce and those disputing whether the rubric applies." with "LLM appraisal is usually
       judged by agreement, which hides failed judgments and scope disputes.";
    7. delete piece 4, "(D points, L to U)" (the numbers stay in §5.5);
    8. delete "on the same papers" from piece 3 (it stays in §5.5);
    9. replace "three models from different providers" with "three models" (the providers stay in §1 and §4).
    - Nothing else is cut, and the stop clause is never cut. The test builds the longest case with every
      placeholder as the macros it stands for, and shows it fits after cut 9 at the latest, also with piece 8.
- **Highlights.** There are five, the journal's maximum.
  - Highlight 4 states the original pre-registered result, as now.
  - The replication highlight **replaces highlight 3** (the 19 rubric changes, which the abstract also
    states), at most 85 characters. It is the **first** line of this list that matches:
    - D7's disagreement sentence applies (any reading): "Replication: sensitivity analyses do not all support the reading";
    - transfers, when B's first hazard row applies (dependence): "Replication: refined rubric's gain depended on hazard-detector papers";
    - transfers, not shown or beyond the bound: "Pre-registered replication: refined rubric resolved more panels";
    - transfers, within the bound: "Replication: refined rubric resolved more panels, by under 10 points";
    - not detected, within the bound: "Replication: no difference detected; 10-point differences excluded";
    - not detected, not shown: "Pre-registered replication: no difference detected";
    - not detected, beyond the bound: "Pre-registered replication: an inconclusive result";
    - reverses, any: "Replication: published rubric resolved more panels than the refined".
- **Conclusion.** A, then B's hazard-dependence sentence if it applies, then the conclusion's D7 sentence if
  D7's disagreement applies, then C. The conclusion's next-study sentence is kept. The conclusion's D7 sentence
  names its subject, because v2.0's post hoc BCa precedes it: "The replication's pre-registered sensitivity
  analyses (a permutation test and a bias-corrected and accelerated interval) do not all support this
  reading." (For *not detected*: "… do not all agree with this reading.")
- **Figure 2.** The replication's interval is added as a solid row labelled "replication (pre-registered)",
  below the original test's rows. The original stopped row stays solid, and the completed row stays hollow
  and grey. The ablation is not drawn in Figure 2.

## 4. The ablation (exploratory): one neutral sentence for every outcome

In §5.3 and §6.4:

> "In an exploratory arm whose procedure omitted the two sentences on how semicolons and OR combine, compared
> on `\replAblPaperExecutions{}` paper-executions of `\replAblPapersCompared{}` papers, resolved panels
> differed from v1.0's by `\replAblResolvedDiff{}` [`\replAblResolvedLow{}`, `\replAblResolvedHigh{}`]
> and panels with a score above 0 by `\replAblAboveZeroDiff{}` [`\replAblAboveZeroLow{}`,
> `\replAblAboveZeroHigh{}`] (95% intervals, not adjusted for the number of measures)."

- **Fewer than 10 papers compared in the ablation** (after a stop): this replaces the sentence above. "The
  exploratory arm was compared on only `\replAblPaperExecutions{}` paper-executions of
  `\replAblPapersCompared{}` papers; its results are in the supplement." With none: "The exploratory arm was
  not compared, because the run stopped before any paper-execution was complete in its arms."
- **Limitation sentence,** always: "The arm removed both operator rules, which can push scores in opposite
  directions, so a difference or its absence cannot be credited to either one; it removed them only from the
  v1.0 procedure, three sentences that bear on them stayed (on supporting every required component, on P3's
  joint requirement, and on applying a criterion's alternatives), as did the common protocol's instruction to
  use the conservative lower supported level, and v1.2 revision 3, which states the rules
  in its rubric, was not ablated."
- **No inference sentence.** Nothing says that the convention did or did not matter, and no interval is
  described as showing an effect.
- **Per pillar:** the results are given in the supplement table, with no sentence selecting a pillar.
- **The semicolon paragraph (§5.3).** The sentence "The original procedure already stated the conjunctive
  reading (ruling D2), so every arm of every test applied the criteria with the convention stated, and the
  study does not measure how models read the criteria without it." becomes "The original procedure already
  stated the conjunctive reading (ruling D2), so every arm of the earlier tests applied the criteria with the
  convention stated." It is followed by the neutral sentence and the limitation sentence. Nothing else in that
  paragraph changes because of the ablation.
- **§6.4.** "(we did not test the models without it)" becomes "(an exploratory arm without it is reported in
  Section~\ref{sec:catalogue})". The neutral sentence follows directly after the sentence that contains it.

## 5. Where everything else goes

- **Supplement:** a new section gives REPL_RUN.md's tables in full, for both comparisons: every added measure
  with both intervals, by pillar, the permutation test, BCa, coverage, request paths and cost. Each measure is
  labelled confirmatory, descriptive or exploratory, as in the pre-registration.
- **Threats to validity (`tab:threats`):**
  - add a row: "Replication on the same papers" & "Pre-registered as a replication of the procedure" & "It
    tests the procedure again, not new papers; one run of each arm pair.";
  - the other rows change only as in "Other article passages" below.

### Methods: the replication paragraph (fixed now)

Added at the end of the subsection "Stages and pre-registration" (§4.6), with the release link in place of
*[link]*:

> "A replication, pre-registered as v3.0 *[link]*, re-ran the new-literature test on the same 57 papers with
> three interleaved arms: v1.2 revision 3 with H5, v1.0 with the original procedure, and, as an exploratory
> arm, v1.0 with the procedure's two sentences on how semicolons and OR combine removed. Each arm had two
> executions of the independent round only (1,026 requests), and each comparison used the paper-executions
> complete in its own two arms. Besides the three-way reading, an equivalence reading asked whether the 90%
> interval excluded differences of 10 points or more. The bound was chosen for feasibility after the original
> test's results on these papers were known, not as a smallest effect of interest. The exploratory arm kept
> three sentences that bear on the rules, and the common protocol's instruction to use the conservative lower
> supported level."

### Other article passages that state the transfer evidence (fixed now, per outcome)

In `docs/chapter-draft/ch2_article.tex`, quoted as they stand. Nothing else in these passages changes. When
D7's disagreement sentence applies, each per-outcome replacement below (the introduction, the threats row and
§6.2's added sentence) ends with ", though its pre-registered sensitivity analyses did not all agree" before
its final punctuation. When B's hazard-dependence row applies, §6.2's transfers sentence reads "…then found a
gain that depended on the hazard-detector papers (D points [L, U]).". "Not
detected" without "within the bound" includes "beyond the bound". Apply the conclusion's replacement before the
introduction's, because the introduction's quoted text also occurs inside the conclusion's.

| Passage | transfers | not detected, within the bound | not detected, otherwise | reverses | fewer than 10 papers |
|---|---|---|---|---|---|
| Introduction: "The evidence on transfer is therefore inconclusive," (the rest of the sentence stays) | "A later pre-registered replication on the same papers found a gain," (with B's hazard-dependence row: "A later pre-registered replication on the same papers found a gain that depended on the hazard-detector papers,") | "A later pre-registered replication on the same papers detected no difference and excluded differences of Δ points or more," | "The evidence on transfer remains inconclusive after a pre-registered replication on the same papers," | "A later pre-registered replication on the same papers found that v1.0 resolved more panels," | "The evidence on transfer remains inconclusive (a pre-registered replication stopped early)," |
| Conclusion: "The evidence on transfer is therefore inconclusive, and paper mix may explain part of the difference." | replaced, in this place, by A, then B's hazard-dependence sentence if it applies, then the conclusion's D7 sentence if D7's disagreement applies, then C | same | same | same | the descriptive-only sentence |
| Threats row "Testing on papers the rubric was refined from", third cell: "on new papers the evidence is inconclusive." | "on new papers a pre-registered replication found a gain." | "on new papers a pre-registered replication detected no difference and excluded differences of Δ points or more." | "on new papers the evidence remains inconclusive after a pre-registered replication." | "on new papers a pre-registered replication found v1.0 ahead." | "on new papers the evidence remains inconclusive (the replication stopped early)." |

- **Threats row "Hazard detectors in scope by our ruling", third cell.** "Only the reading of the unseen-corpus
  gain changes (its interval then includes zero)." becomes "The reading of the unseen-corpus gain changes (its
  interval then includes zero)", followed by one clause:
  - "; the replication's reading does not change." when the reading without hazard detectors equals the main
    reading;
  - "; the replication's reading changes to *[sensitivity reading]*." when it differs;
  - "; too few replication papers without hazard detectors were compared to tell." when it was not applied.
- **Every outcome, fixed text:**
  - introduction: ", and the gain on the refinement papers is reported, as pre-registered, as specific to
    them." becomes ", and the gain on the refinement papers is reported, as pre-registered for the original
    test, as specific to them.";
  - threats row "Testing on papers the rubric was refined from": "The exposed-corpus gain is specific to those
    papers;" becomes "The exposed-corpus gain is reported, as pre-registered for the original test, as specific
    to those papers;";
  - §6.2: "The study tested refinement three times on papers the refinement had not used." becomes "The study
    tested refinement three times on papers the refinement had not used, and re-ran the last test as a
    pre-registered replication.";
  - §6.2: "Two of the three refinements therefore looked better on the papers they were developed from than
    on fresh papers," becomes "Two of the three refinements therefore looked better on the papers they were
    developed from than on fresh papers in their original tests,";
  - Table 1 (the related-work comparison), this study's row: "pre-registered (2 tests)" becomes
    "pre-registered (3 tests)";
  - §2: "Our final test applies this time split" becomes "Our final test and its replication apply this time
    split";
  - threats row "The authors refine and test their own rubric": "final test pre-registered" becomes "final test
    and its replication pre-registered".
- **§6.2, by outcome.** After "None of this replaces the pre-registered reading." add one sentence:
  - transfers: "A pre-registered replication on the same papers then found a gain (D points [L, U]).";
  - not detected, within the bound: "A pre-registered replication on the same papers then detected no
    difference and excluded differences of Δ points or more.";
  - not detected, otherwise: "A pre-registered replication on the same papers then detected no difference (D
    points [L, U]).";
  - reverses: "A pre-registered replication on the same papers then found that v1.0 resolved more panels (D
    points [L, U]).";
  - fewer than 10 papers: "A pre-registered replication on the same papers stopped early and is reported
    descriptively."
- **Figure 2 caption.** Add "The replication row is pre-registered (v3.0); no replication row without hazard
  detectors is drawn."
- **The general rule for anything not listed here.** Any other article sentence that states the state of the
  transfer evidence, or the number or order of pre-registered tests, may change only to agree with the
  sentences fixed in these rules, reusing their wording. Each such change is listed, with its old and new text,
  in a dated table in the supplement's deviations section, and the Goal B audit checks every one. Nothing else
  may change.
- **Threats row "Raters may have seen the papers in training", second cell.** "Final test on papers published
  after the review's search" becomes "Tests on papers published after the review's search (the original test
  and its replication)".
- **Deviations:** any deviation from v3.0, including a resume, is listed with its date in the supplement and
  named in §5.5.
