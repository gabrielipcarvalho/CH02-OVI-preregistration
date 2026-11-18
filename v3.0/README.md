# CH02 pre-registration v3.0: replication of the new-literature test, with an operator-rule ablation

This folder is the release v3.0 of `gabrielipcarvalho/CH02-OVI-preregistration`, prepared in the private
research repository. It must be published **before the freeze and before the first rated request**.
GitHub records the release date on its own servers.

| File | Content |
|---|---|
| `PREREGISTRATION_REPLICATION.md` | The questions, the three arms, the 57 papers, the measures, the readings, the equivalence bound, the stopping rules and the cost condition |
| `REPORTING_RULES_REPLICATION.md` | The sentences that report each possible outcome, fixed before the run |
| `HANDBOOK_EVAL_ORIGINAL_NOCONJ.txt` | The ablation arm's procedure: the original procedure minus two sentences |
| `CH02_prereg_v3_81895c8.zip` | The exact files from the research repository at commit `81895c8e15218d62a7e73e1c9b526356ef8ea429`: rubrics, procedures, protocol, schema, input hashes, the v2.0 pre-registration, runner and analysis code with their tests, the dry-run freeze and the parity check |
| `CODE_HASHES.json` | sha256 of the runner and analysis files; the launch is refused if the code differs |
| `SOURCE_COMMIT.txt` | The source commit |
| `SHA256SUMS.txt` | sha256 of every file above |

The research repository is private. No paper text, figure image, quotation or provider data is included.
Results will be reported against this plan, and every deviation will be dated.

## Publishing (Gabriel; nothing here has been pushed)

1. Check the folder: `cd docs/rerun-2026-11/prereg-release && shasum -a 256 -c SHA256SUMS.txt` (every line OK).
2. Read PREREGISTRATION_REPLICATION.md and REPORTING_RULES_REPLICATION.md once more. Approve them, or ask for
   changes (the folder is then rebuilt).
3. Update the local clone and look at how v2.0 is laid out:
   `cd ~/Projects/Griffith/CH02_preregistration_2026-10-28 && git pull && git log --oneline -3 && ls`.
4. Copy the files in, following v2.0's layout. If v2.0 sits in its own folder, use one named `v3.0/`:
   `mkdir -p v3.0 && cp ~/Projects/Griffith/CH2-Framework-Validation/docs/rerun-2026-11/prereg-release/* v3.0/`
   then `cd v3.0 && shasum -a 256 -c SHA256SUMS.txt && cd ..`.
5. Commit and push: `git add v3.0 && git commit -m "Pre-registration v3.0: replication and operator-rule
   ablation (source commit 81895c8)" && git push`.
6. Create the release: `gh release create v3.0 --title "v3.0: replication of the new-literature test" --notes
   "Published before the freeze and the first rated request. See v3.0/PREREGISTRATION_REPLICATION.md."
   v3.0/*` (or create it on github.com, tag `v3.0`, attaching the same files).
7. Paste the release URL into `docs/rerun-2026-11/04_PROGRESS.md` (task E4). Goal B starts only after that,
   once you have pasted your balances and said go.
