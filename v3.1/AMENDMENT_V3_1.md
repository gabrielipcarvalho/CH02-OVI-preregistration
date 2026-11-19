# Amendment v3.1 to pre-registration v3.0: the replication is the primary result on transfer

**Status:** written on 19 November 2026 while the replication run was in progress (launched 19:39 local,
19 November) and **before any result of it was computed**: `scripts/repl_report.py` had not been run on any of
its data. What had been seen of the run: the chain's status file (start line only), the count of requests
ended and their statuses (totals only, from the runner's log), and the tail of the runner's error log. No
score, judgment or comparison had been looked at, and the live ledger had not been queried. To be published
as v3.1 of `gabrielipcarvalho/CH02-OVI-preregistration`; GitHub records the release date. Provenance:
agent:claude-opus-5-5, from a rule proposed by a co-author on 19 November 2026 and adopted by the first author
the same day.

It amends [PREREGISTRATION_REPLICATION.md](PREREGISTRATION_REPLICATION.md) and
[REPORTING_RULES_REPLICATION.md](REPORTING_RULES_REPLICATION.md) (both v3.0). **This file wins wherever v3.0
conflicts with it;** §3.13 lists the v3.0 passages it replaces. Everything else in v3.0 stands.

Notation as in v3.0 (D, L, U, Δ, n, with n = `\replPapersCompared{}`). Article passages are quoted from
`docs/chapter-draft/ch2_article.tex` as they stand; figures are named by their LaTeX labels. "A final stop"
means a final stop under v3.0's stopping rules.

## 1. Why

Once the replication finishes, the article will hold three readings of the same comparison: the original
test's stopped comparison (its pre-registered result, *not detected*), its completed comparison (a declared
deviation, *transfers* when the rule is applied descriptively), and the replication. Deciding which one leads
after seeing all three would be choosing a headline from a menu. This amendment fixes the choice before the
replication's numbers exist.

## 2. The rule

It replaces v3.0's passage "It does not replace the v2.0 result: … this test is reported separately with its
own reading" and the second bullet of REPORTING_RULES §1.

- **The replication is the article's primary result on whether the refinement's gain transfers to the 57
  papers published after the review,** because it is the clean test: every rule, measure, stopping condition
  and reporting sentence was fixed before its first request. It is reported with its own reading. The papers
  are new to the refinement, not to the study: the replication tests the procedure again on the original
  test's papers.
- **The original test (v2.0) is reported as the earlier test, whose procedure was compromised:** its run
  stopped on a provider error that its declared policy would have re-requested, the decision to resume came
  after the stopped result was known, and its reporting rules were written during the run. Within that test,
  the stopped comparison remains its pre-registered result and the completed comparison remains a declared
  deviation. Its results and readings are not changed, and its fixed sentences (OUTCOME_RULES.md §2;
  RESUME_REPORTING_RULES.md) stay verbatim, with two declared exceptions, both dated deviations from v2.0's
  rules, made on 19 November 2026 before any replication result:
  - highlight 4 gains the word "Earlier" (§3.9);
  - the abstract's "reported, as pre-registered, as specific to them" becomes "reported, as an earlier test
    had pre-registered, as specific to them" (§3.3).
- **The rule holds whatever the replication shows,** including a final stop, fewer than 10 papers compared, or
  none. The replication's result is reported with v3.0's sentences for its reading and equivalence reading,
  unchanged except as this file says. If it detects no difference, those are v3.0's *not detected* sentences,
  including the word "inconclusive" where v3.0 uses it.

## 3. What changes

### 3.1 How the replication's sentences name their papers and role (outside the abstract)

Two fixed phrases, by case:

| Case | Papers phrase **P** | Role phrase **R** |
|---|---|---|
| no final stop, all 57 papers compared | "on the 57 papers published after the review (the primary test)" | "(the primary test)" |
| no final stop, 10 to 56 papers compared | "on n of the 57 papers published after the review (the primary test)" | "(the primary test)" |
| a final stop, 10 to 56 papers compared | "on n of the 57 papers published after the review (the primary test, stopped finally)" | "(the primary test, stopped finally)" |
| a final stop, all 57 papers compared | "on the 57 papers published after the review (the primary test, stopped finally)" | "(the primary test, stopped finally)" |

- **Sentence A (all nine rows):** "In a pre-registered replication on the same papers," becomes "In a
  pre-registered replication P,".
- **§2's "fewer than 10 papers" sentence** begins "The pre-registered replication on the 57 papers published
  after the review (the primary test) stopped finally after …"; the rest is v3.0's, including the ending at
  "n papers compared" when no paper was compared.
- **One paper.** In every "fewer than 10 papers" sentence (v3.0's and this file's), "n papers compared"
  reads "1 paper compared" when n is 1.
- **D4** is followed, whenever D4 is reported (that is, when A to D are reported), by "The papers are new to
  the refinement, not to the study."
- The threats row "Replication on the same papers" (added by v3.0 §5) and v3.0's clause for the threats row
  "Hazard detectors in scope by our ruling" keep v3.0's wording in every case, including no paper compared.

### 3.2 §5.5 (sec:postreview): the replication first, the relation last

This replaces, for §5.5, v3.0 §2's "always in this order: A, then B, then C, then D".

1. At the start of §5.5, before "\paragraph{The run stopped}": `\subsubsection{The replication (primary)}`,
   then A, B and D1–D7, or, with fewer than 10 papers compared, §2's "fewer than 10 papers" sentence alone.
2. Then `\subsubsection{The original test}`, with one fixed sentence: "The original test (v2.0) is reported
   next as the earlier test, whose procedure was compromised: its run stopped on a provider error that its
   declared policy would have re-requested, and the decision to resume came after its stopped result was
   known."
3. Then the original test's existing paragraphs and table, unchanged except:
   - the heading "Primary result" becomes "Its pre-registered result";
   - the heading "Which comparison is primary" becomes "Which of its comparisons is primary";
   - "We keep the stopped comparison as primary" becomes "We keep the stopped comparison as the original
     test's primary result";
   - "Without the hazard-detector papers, the primary difference was" becomes "Without the hazard-detector
     papers, the original test's primary difference was";
   - "as in the primary." becomes "as in the original test's primary.";
   - "including the \prPaperExecutions{} of the primary," becomes "including the \prPaperExecutions{} of the
     original test's primary,".
4. Last in §5.5: `\subsubsection{The two tests}` with C in the form of §3.7. With fewer than 10 papers
   compared, there is no C and no such subsubsection.

### 3.3 The abstract: the replication first

- **In the sentence on the 16.7-point gain,** "reported, as pre-registered, as specific to them." becomes
  "reported, as an earlier test had pre-registered, as specific to them."
- **Order:** that sentence; then the replication's sentence; then the lead-in **"It repeated an earlier,
  procedurally compromised test."**; then the original test's sentences, verbatim, from "On papers published
  after the rubric's source review" to the end of the kind-of-agreement sentence; then v3.0's closing
  sentence.
- **The replication's sentence** is v3.0's pieces 1–8, with piece 3 reading "on papers published after the
  rubric's source review found the revision resolved more panels" (likewise "… detected no difference" and
  "… found the revision resolved fewer panels"). After a final stop, piece 2 ("(stopped after … of 1,026
  requests)") carries the stop. The abstract carries no "(the primary test)": the first place, the lead-in
  and the closing sentence, which follows the replication's reading (v3.0 §3), carry the role.
- **Fewer than 10 papers compared:** "A pre-registered replication on papers published after the rubric's
  source review stopped early with n papers compared and is reported descriptively." With none compared: "A
  pre-registered replication on papers published after the rubric's source review stopped before any paper
  was compared." The lead-in follows either; with none compared it reads "It was to repeat an earlier,
  procedurally compromised test."
- **Cuts,** replacing v3.0's list. They are made in this order, and only as far as needed to reach 250 words:
  - a. to f. v3.0's cuts 1 to 6, unchanged;
  - g. delete "A refined procedure did not transfer to 15 held-out papers." (the held-out result stays in the
    contributions, §5.1 and §6.2);
  - h. v3.0's cut 9: "three models from different providers" becomes "three models";
  - i. "(agreed score or ``not applicable''; +11.0 to +22.9)" becomes "(agreed score or ``not
    applicable'')" (the interval stays in §5.4 and §5.5);
  - j. "As a case, three models" becomes "Three models";
  - k. in piece 3, "on papers published after the rubric's source review" becomes "on later papers" (the
    original test's sentence that follows names the papers).

  v3.0's cut 7, which deleted the replication's "(D points, L to U)", and v3.0's cut 8 are withdrawn. The
  replication's difference and interval are never cut, and neither is the stop clause.
- **Counting words.** Words are the whitespace-separated tokens of the abstract's source text, with
  punctuation attached to the word before it and each macro counted as one word, as v3.0's test counts them.
- `tests/test_repl_run.py` builds the longest case (a final stop, transfers, beyond the bound, hazard
  dependence; with and without D7's sentence). It includes the lead-in, every placeholder as the macros it
  stands for, and all cuts, and joins the pieces as the sentence reads. The result is 250 words with
  D7's sentence and 248 words without.

### 3.4 Contribution item 3 (the introduction): the replication first

- **Title:** "A pre-registered test of the refinements on papers published after the review's literature
  search" becomes "Pre-registered tests of the refinements on papers published after the review's literature
  search".
- **After "points of resolved panels on the papers it was refined from."** insert, by outcome (P as in §3.1):

  | Outcome | Inserted sentence |
  |---|---|
  | transfers | "A pre-registered replication P found a gain." With B's hazard-dependence row: "A pre-registered replication P found a gain that depended on the hazard-detector papers." |
  | not detected, within the bound | "A pre-registered replication P detected no difference and excluded differences of Δ points or more." |
  | not detected, otherwise | "The evidence on transfer is inconclusive after a pre-registered replication P." |
  | reverses | "A pre-registered replication P found that v1.0 resolved more panels." |
  | fewer than 10 papers | "A pre-registered replication on the 57 papers published after the review (the primary test) stopped early and is reported descriptively." |
  | no paper compared | "A pre-registered replication on the 57 papers published after the review (the primary test) stopped before any paper was compared." |

  When D7's disagreement sentence applies, the inserted sentence ends with ", though its pre-registered
  sensitivity analyses did not all agree" before its full stop.
- "On new papers the pre-registered comparison" becomes "In an earlier, procedurally compromised test on those
  papers, the pre-registered comparison".
- "gave a smaller gain" becomes "gave a gain smaller than 16.7 points".
- "The evidence on transfer is therefore inconclusive, and the gain on the refinement papers is reported, as
  pre-registered, as specific to them." becomes "The gain on the refinement papers was reported in the
  original test, as pre-registered, as specific to them."
- "An earlier pre-registered test showed the same pattern for the application procedure: refined on eight
  development papers, it raised" becomes "The held-out evaluation, also pre-registered, tested the application
  procedure, which, refined on eight development papers, raised".

### 3.5 The conclusion: the replication first

- "The final rubric revision gained 16.7 points on its source papers; on papers published after the review,
  in a pre-registered test that stopped part-way, no difference was detected (\prResolvedDiff{} points,
  \prResolvedLow{} to \prResolvedHigh)." becomes:
  1. "The final rubric revision gained 16.7 points on its source papers."
  2. A (as in §3.1); then B's hazard-dependence sentence, if it applies; then the conclusion's D7 sentence, if
     it applies. With fewer than 10 papers compared, §2's "fewer than 10 papers" sentence (as in §3.1) takes
     the place of A, B and D7.
  3. "In the earlier test of the same question, whose procedure was compromised, the pre-registered comparison
     stopped part-way and detected no difference (\prResolvedDiff{} points, \prResolvedLow{} to
     \prResolvedHigh)."
- "which does not change the pre-registered reading" becomes "which does not change the original test's
  pre-registered reading". The rest, to "(both post hoc).", is unchanged.
- "The evidence on transfer is therefore inconclusive, and paper mix may explain part of the difference." is
  replaced by C in the form of §3.7. With fewer than 10 papers compared, there is no C and this sentence stays
  unchanged.

### 3.6 §6.2 (Refinement gains measured where the refinement was made)

- "The study tested refinement three times on papers the refinement had not used." becomes, as in v3.0, "The
  study tested refinement three times on papers the refinement had not used, and re-ran the last test as a
  pre-registered replication."
- "final revision gained 16.7 points on the 42 papers it was written from; on new papers the pre-registered"
  becomes "final revision gained 16.7 points on the 42 papers it was written from. *[§6.2 sentence]* In the
  earlier, procedurally compromised test, on new papers the pre-registered". The §6.2 sentence is, by outcome
  (P as in §3.1):
  - transfers: "A pre-registered replication P found a gain (D points [L, U])." With B's hazard-dependence
    row: "A pre-registered replication P found a gain that depended on the hazard-detector papers (D points
    [L, U]).";
  - not detected, within the bound: "A pre-registered replication P detected no difference and excluded
    differences of Δ points or more.";
  - not detected, not shown: "A pre-registered replication P detected no difference (D points [L, U]).";
  - not detected, beyond the bound: "A pre-registered replication P gave an inconclusive result (D points [L,
    U]).";
  - reverses: "A pre-registered replication P found that v1.0 resolved more panels (D points [L, U]).";
  - fewer than 10 papers: "A pre-registered replication on the 57 papers published after the review (the
    primary test) stopped early and is reported descriptively.";
  - no paper compared: "A pre-registered replication on the 57 papers published after the review (the
    primary test) stopped before any paper was compared.".

  When D7's disagreement sentence applies, the §6.2 sentence ends with ", though its pre-registered
  sensitivity analyses did not all agree" before its full stop.
- "None of this replaces the pre-registered reading." becomes "None of this replaces the original test's
  pre-registered reading." No sentence is added after it.
- "Two of the three refinements therefore looked better on the papers they were developed from than on fresh
  papers," becomes "Two of the three refinements looked better on the papers they were developed from than on
  fresh papers in their original tests,".
- "exceeded the new-literature gain by" becomes "exceeded the original test's gain by".
- "and without the new papers the 16.7-point gain would have been reported as the effect of the refinement."
  becomes "and without the new papers the 16.7-point gain would have been reported without a test on papers
  it was not written from."
- After "is the pattern a fresh test set exists to catch \citep{dwork2015reusable,recht2019imagenet}." insert,
  by outcome. U is compared with +16.7 as the 4-decimal value in REPL_RUN.json (0.167), as in v3.0 B:
  - transfers, U below +16.7: "For the final revision, the primary test then found a gain on the new papers
    whose 95% interval lies below the 16.7 points gained on its source papers.";
  - transfers, U at or above +16.7: "For the final revision, the primary test then found a gain on the new
    papers whose 95% interval does not exclude the 16.7 points gained on its source papers, so for this
    revision the pattern rests on the earlier test alone.";
  - transfers with B's hazard-dependence row, U below +16.7: "For the final revision, the primary test then
    found a gain on the new papers that depended on the hazard-detector papers; its 95% interval lies below
    the 16.7 points gained on its source papers.";
  - transfers with B's hazard-dependence row, U at or above +16.7: "For the final revision, the primary test
    then found a gain on the new papers that depended on the hazard-detector papers; its 95% interval does
    not exclude the 16.7 points gained on its source papers, so for this revision the pattern rests on the
    earlier test alone.";
  - not detected, within the bound or not shown: "For the final revision, the primary test then detected no
    difference on the new papers.";
  - not detected, beyond the bound: "For the final revision, the primary test then gave an inconclusive
    result on the new papers.";
  - reverses: "For the final revision, the primary test then found v1.0 ahead on the new papers.";
  - fewer than 10 papers: "For the final revision, the primary test stopped early and is reported
    descriptively.";
  - no paper compared: "For the final revision, the primary test stopped before any paper was compared."

  When D7's disagreement sentence applies, this sentence too ends with ", though its pre-registered
  sensitivity analyses did not all agree" before its full stop.

### 3.7 C when it does not follow A (§5.5 and the conclusion)

| Reading (and equivalence) | C |
|---|---|
| transfers | "The replication differs in reading from the original test's pre-registered comparison, which detected no difference, and agrees in reading with its completed comparison, a declared deviation." |
| not detected, within the bound or not shown | "Like the original test's pre-registered comparison, the replication detected no difference; the original test's completed comparison, a declared deviation, gave *transfers*." |
| not detected, beyond the bound | "The replication is reported beside both comparisons of the original test, without a reading." |
| reverses | "The replication differs in reading from both comparisons of the original test." |

### 3.8 The threats table (tab:threats)

- **Row "Testing on papers the rubric was refined from", third cell.** "The exposed-corpus gain is specific to
  those papers;" becomes "The exposed-corpus gain was reported in the original test, as pre-registered, as
  specific to those papers;". The clause after it, "on new papers the evidence is inconclusive.", is replaced
  by the clause for the outcome. R is as in §3.1. When v3.0's D7 clause applies, it is added before the full
  stop.

  | Outcome | Clause |
  |---|---|
  | transfers | "on papers new to the refinement a pre-registered replication R found a gain." |
  | not detected, within the bound | "on papers new to the refinement a pre-registered replication R detected no difference and excluded differences of Δ points or more." |
  | not detected, otherwise | "on papers new to the refinement the evidence is inconclusive after a pre-registered replication R." |
  | reverses | "on papers new to the refinement a pre-registered replication R found v1.0 ahead." |
  | fewer than 10 papers | "on papers new to the refinement the evidence remains inconclusive (the replication, the primary test, stopped early)." |
  | no paper compared | "on papers new to the refinement the evidence remains inconclusive (the replication, the primary test, stopped before any paper was compared)." |
- **Row "The stopped, then resumed, run".** "Stopped comparison kept primary;" becomes "Stopped comparison kept
  as the original test's primary;", and "The primary rests on" becomes "The original test's primary rests
  on".

### 3.9 Highlights

As v3.0, the replication highlight replaces highlight 3, directly before the original test's highlight. Two
changes:
- Highlight 4 gains one word at its start: "Earlier pre-registered test: a 16.7-point refinement gain did not
  clearly transfer" (82 characters). This is one of the two declared exceptions in §2.
- With no paper compared, the replication highlight is "Pre-registered replication stopped before any paper
  was compared" (64 characters), not v3.0's "… stopped early; reported descriptively".

### 3.10 Figures

- **fig:effects.**
  - The replication row is drawn **at the top**, all compared papers only:
    - at least 10 papers compared: solid, labelled "Replication, v1.2 r3 (pre-registered, primary)".
      After a final stop, ", stopped, n of 57" is added. When fewer than 57 papers were compared without a
      final stop, ", n of 57" is added;
    - fewer than 10: hollow and dashed, labelled "Replication, v1.2 r3 (primary; stopped; descriptive)";
    - no paper compared: no row.
  - The original test's rows are labelled "Original test, v1.2 r3" in place of "New-literature test, v1.2
    r3", with their parentheses unchanged.
- **fig:outcomes** (drawn by `fig_stages` in `scripts/article_figures.py`). Its two stages labelled "New
  literature" (stopped; resumed) are labelled "Original test", with their parentheses unchanged. No
  replication stage is added (v3.0 adds none).
- **fig:design and fig:story** keep their labels. They show no replication, so "new literature" names the
  original test without ambiguity.
- **tab:corpus.**
  - In the caption, "New-literature test: 57 papers planned" becomes "New-literature tests (the replication
    and the original test): 57 papers planned".
  - "\emph{New-literature test: v1.2 revision 3, pre-registered}" becomes "\emph{Original test: v1.2
    revision 3, pre-registered}".
  - "\emph{New-literature test, resumed run" becomes "\emph{Original test, resumed run".
  - Directly above the original test's block, a replication block is added, with numbers from the report's
    macros only:
    - heading `\multicolumn{5}{l}{\emph{Replication: v1.2 revision 3, pre-registered (v3.0); the primary
      test}}`;
    - rows "Resolved, R0 (primary)" (`\replResolvedFirst`, `\replResolvedSecond`, `\replResolvedDiff`,
      [`\replResolvedLow`, `\replResolvedHigh`]), "Complete and agreeing" (`\replCA…` likewise) and
      "Resolved, R0, without hazard detectors" (`\replNoHazard…` likewise).
    - After a final stop with at least 10 papers compared, the heading ends "; stopped, n papers". With 1
      to 9 papers compared, it ends "; stopped, descriptive only". With no paper compared, it ends ";
      stopped" and the three rows become one: `\multicolumn{5}{l}{--- (no paper compared)}`.
- **fig:effects caption.** "The pre-registered new-literature row covers" becomes "The original test's
  pre-registered row covers". v3.0's added caption sentence becomes "The replication row (top) is the
  pre-registered primary test (v3.0, amended by v3.1); no replication row without hazard detectors is drawn."
  With no paper compared, there is no row and no added sentence.
- **fig:design caption.** "(the pre-registered primary)" becomes "(the original test's pre-registered
  primary)".

### 3.11 Methods: one sentence, fixed now

Appended to v3.0's Methods replication paragraph (end of "Stages and pre-registration"), with the release link
in place of *[link]*:

> "Before any result of the replication was computed, an amendment (v3.1 *[link]*) made the replication the
> primary result on transfer to these papers and reported the original test as the earlier, procedurally
> compromised test, whatever the replication showed."

### 3.12 Other sentences that call the original test's comparison "the primary"

| Where | Old | New |
|---|---|---|
| Glossary, "Stopped and completed comparisons" | "(the primary result)" | "(the original test's primary result)" |
| Timeline table (tab:timeline), 04:19 row | "the pre-registered primary, read as" | "the original test's pre-registered primary, read as" |
| Timeline table, last row | "reported beside the primary and not adjusted" | "reported beside the original test's primary and not adjusted" |
| tab:corpus caption | "The stopped comparison is the pre-registered one:" | "The original test's stopped comparison is its pre-registered one:" |
| Methods, "Stages and pre-registration" | "The stopped comparison is the pre-registered result;" | "The stopped comparison is that test's pre-registered result;" |
| §5.5 heading | "\subsection{The new-literature test}" | "\subsection{The new-literature tests}" |
| Introduction, before the contributions | "(Figure~\ref{fig:story} summarises the second and third)" | "(Figure~\ref{fig:story} summarises the second)" |
| Introduction, second paragraph | "and, finally, in a pre-registered test on papers published after the review." | "and, finally, in a pre-registered test, and then its pre-registered replication, on papers published after the review." |
| Methods, stage overview | "and finally tested on 57 papers published after the review's search." | "and finally tested on 57 papers published after the review's search, in a pre-registered test and its pre-registered replication." |
| Glossary, "Stopped and completed comparisons" | "In the new-literature test: the pre-registered comparison" | "In the original test: the pre-registered comparison" |
| Rubric description (§3) | "no rater scored P3 above 0 in any test;" | "no rater scored P3 above 0 in any test before the replication;" |
| §6.2, "Two pillars behave differently" | "P3 received no score above 0 from any rater in any test, so" | "P3 received no score above 0 from any rater in any test before the replication, so" |
| §6.7, the gate's structure | "P3 received no score above 0 from any rater in any test." | "P3 received no score above 0 from any rater in any test before the replication." |

**Deviations from v3.0** (v3.0 §5: "named in §5.5") are named in the replication's subsubsection, directly
after D6; when there is no D6, or the "fewer than 10 papers" sentence replaces A to D, at the end of that
subsubsection.

"The pre-registered reading is" in §5.5 is not changed. It stands inside the original test's own subsection,
after its lead-in. Any other sentence found later is handled by v3.0 §5's general rule and listed in the
supplement's dated table.

### 3.13 The v3.0 passages this file replaces

- PREREGISTRATION_REPLICATION.md: "It does not replace the v2.0 result: … reported separately with its own
  reading." (§2 here).
- REPORTING_RULES_REPLICATION.md:
  - §1, first bullet's "reported exactly as now", for the renamings of §3.2, §3.6, §3.8, §3.10 and §3.12;
  - §1, second bullet (§2 here), and, for the two declared exceptions only, §1's first bullet ("their fixed
    sentences … are not edited"), §3's "What stays" and §3's "Highlight 4 states the original pre-registered
    result, as now" (§2, §3.3, §3.9).
  - §2:
    - the opening "always in this order: A, then B, then C, then D", for §5.5 and the conclusion (§3.2, §3.5);
    - sentence A's opening phrase, and the opening of the "fewer than 10 papers" sentence (§3.1);
    - an addition after D4 (§3.1);
    - from the "fewer than 10 papers" block: its "Conclusion: this sentence alone" (§3.5), its highlight when
      no paper was compared (§3.9) and its Figure 2 label (§3.10).
  - §3:
    - the abstract's placement, piece 3, the "fewer than 10 papers" sentence and the cuts; the 16.7 clause
      (§3.3);
    - the conclusion bullet (§3.5) and the Figure 2 bullet (§3.10).
  - §5:
    - the introduction, conclusion and threats rows of the per-outcome table (§3.4, §3.5, §3.8);
    - the fixed-text changes to the introduction's and the threats row's "specific to" clauses (§3.4, §3.8);
    - the §6.2 bullets (§3.6);
    - the general rule, for the renamed passages of §3.10 and §3.12, which are fixed here;
  - v3.0 §2's sentence C, reworded to name the replication where it does not follow A (§3.7);
  - v3.0 §5's fixed Methods paragraph, which gains one sentence (§3.11);
    - the Figure 2 caption bullet (§3.10).

### 3.14 The field result (no agreed profile above zero), fixed now

From REPL_RUN.json, take the four gate tables `confirmatory.ovi_gate_profiles.REPL_V12.gates`,
`confirmatory.ovi_gate_profiles.REPL_V10.gates`, `exploratory_ablation.ovi_gate_profiles.REPL_V10_NOCONJ.gates`
and `exploratory_ablation.ovi_gate_profiles.REPL_V10.gates` (the two REPL_V10 tables are built from
different paper-executions after a stop, so both are read). The rule uses only two yes/no tests, never a
count, so a profile present in both REPL_V10 tables does no harm: "A > 0" means some table has a key `ovi_N`
(any N ≥ 0) with a count above zero, and "K > 0" means some table has a key `ovi_N` with N ≥ 1 and a count
above zero. Each table covers the paper-executions complete in both arms of its comparison, so the sentences below speak
of the paper-executions the replication compared, its exploratory arm included.

- **A = 0, that is, not A > 0** (no agreed profile, including when no paper was compared). In §5.7 (sec:field-result), after "in
  the completed comparison)." insert "The replication had no agreed profile on the paper-executions it compared." Nothing else changes.
- **A > 0 and not K > 0.** In §5.7, after "in the completed comparison)." insert "The replication's agreed
  profiles on the paper-executions it compared were all at zero as well." Nothing else changes.
- **K > 0.**
  - In §5.7, after "in the completed comparison)." insert "In the replication, however, at least one agreed
    profile on the paper-executions it compared was above zero (its profiles are in the supplement)."
  - "no profile examined in any phase reached" becomes "no profile examined in any phase before the
    replication reached".
  - The heading "No agreed in-scope profile documented operational viability" gains " before the
    replication".
  - In the conclusion, "Across every phase, no paper" becomes "Across every phase before the replication, no
    paper".
  - In §6.7 (sec:field), "The OVI-Gate of zero across every phase and every rubric version" becomes "The
    OVI-Gate of zero across every phase before the replication and every rubric version".
  - In the threats table's row "Conservative scoring", "so the OVI-Gate of zero is a statement" becomes "so
    the OVI-Gate of zero before the replication is a statement".
  - Highlight 5 becomes "No paper the models agreed on documented viability before the replication" (73
    characters).

## 4. What does not change, and what else does

**Unchanged:** the arms, the papers, the schedule and seed, the measures, the three-way and equivalence
readings, the equivalence bound, the stopping rules, the ablation and its exploratory status, the cost
condition, the original test's results and readings, and every v3.0 sentence except as §3 says. The run's
code (`pipeline/`, `scripts/repl_chain.sh`, `scripts/repl_report.py`) is not changed.

**Changes beyond the role and order, declared:**
- the two exceptions to v2.0's fixed text in §2 (highlight 4; the abstract's "as an earlier test had
  pre-registered");
- the abstract's piece 3 may shorten to "on later papers" (cut k);
- the abstract may lose the held-out sentence (cut g), the +16.7 interval (cut i) and "As a case," (cut j),
  each only if needed;
- the contribution item's title, "a gain smaller than 16.7 points" and its sentence on the held-out
  evaluation (§3.4);
- the conclusion's sentence on the stopped comparison (§3.5) and §6.2's added sentence after the citation
  (§3.6);
- the figure labels and tab:corpus (§3.10), and the headings and sentences quoted in §3.2, §3.6, §3.8 and
  §3.12;
- sentence C's wording where it does not follow A (§3.7), and one sentence added to v3.0's Methods paragraph
  (§3.11);
- in contribution item 3, "In an earlier, procedurally compromised test on those papers" and "was reported in
  the original test" (§3.4);
- in the conclusion, "the original test's pre-registered reading" (§3.5). This clause follows
  RESUME_REPORTING_RULES' fixed conclusion sentence ("Completing the run as a declared deviation gave [the
  descriptive reading in words]"), whose template ends at the reading, so the fixed sentence is unchanged;
- the field-result sentences in the case §3.14 names.
