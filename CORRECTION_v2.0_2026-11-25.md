# Correction to pre-registration v2.0 (post-SLR evaluation), 25 November 2026

This note corrects and updates release `v2.0` of this repository. The v2.0 files are unchanged; this note is
dated and sits beside them.

1. **Screening and the rubric.** The stage 2 amendment (`PREREGISTRATION_POSTSLR_STAGE2.md`, "Exposure")
   states that in screening "no rubric, pillar or score was involved". This is too strong. The AI assistant
   that screened the records against the review's criteria had also drafted the rubric revisions, and its
   screening notes recorded how some papers would fall under the v1.2 scope statement (for example, people
   detectors and records-based studies as likely out of scope). The scope make-up of the set was therefore
   known before the run. No rater model saw any of the papers before the run, and no rubric text was
   written from them.
2. **The run stopped and was resumed.** The run stopped at request 558 of 684 on an OpenAI HTTP 520 that the
   pre-registered re-request policy (DEC-0011) covered but the runner did not retry. The stopped comparison
   (31 paper-executions, 26 papers) remains this test's pre-registered result, with its pre-registered
   reading. The run was then resumed as a declared deviation, decided after the stopped result was known
   and needing changes to the runner. Its reporting rules were committed while the resumed run was in
   progress, before any of its results was computed. The completed comparison is reported beside the stopped
   one, not in its place.
3. **The replication.** The same comparison was repeated on the same 57 papers, from the start, in a
   replication pre-registered as release `v3.0` (published 18 November 2026, before its first request) and
   amended by release `v3.1` (published 19 November 2026, before any of its results was computed). Under
   v3.1 the replication is the article's primary result on transfer, and this test is reported as the
   earlier test, whose procedure was compromised.

All three points are reported in the article and its supplement.
