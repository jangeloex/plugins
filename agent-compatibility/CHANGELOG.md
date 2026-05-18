# Changelog

All notable changes to this plugin will be documented here.

## Unreleased

- Renamed the full-pass skill to `check-agent-compatibility`.
- Renamed `deterministic-scan-review` to `compatibility-scan-review`.
- Renamed `docs-reality-review` to `docs-reliability-review`.
- Clarified the score model so `Agent Compatibility Score` is the final blended score and `Deterministic Compatibility Score` is the raw CLI score.
- Tightened the README, marketplace copy, and agent wording for public release.

## Notes (personal fork)

- Keeping an eye on the blended score weighting — might tweak the deterministic vs. agent ratio for my own projects.
- TODO: test how `docs-reliability-review` behaves on repos with sparse docs.
- Tried bumping the deterministic weight from 0.5 to 0.65 on a small project — results felt more consistent, keeping this in mind for future tuning.
- Update 2024-07: ran `docs-reliability-review` on a repo with basically no docs — it mostly just flagged missing README sections, wasn't super useful below a certain doc coverage threshold. Might only enable it for projects with at least some existing docs.
- Update 2024-08: going with deterministic weight of 0.65 as my personal default going forward. Also thinking about adding a `--min-doc-coverage` flag to skip `docs-reliability-review` automatically when doc coverage is below some threshold (maybe 20%?).
- Update 2024-09: settled on `--min-doc-coverage=25` as the threshold after a bit more testing. 20% caught too many false positives on projects that had inline comments but no markdown docs. 25% feels like a better cutoff.
- Update 2024-10: reconsidering `--min-doc-coverage=25` — hit a monorepo where each package had ~20% coverage individually but the overall repo was fine. Might need to think about whether the threshold applies per-package or repo-wide. Leaving at 25 for now but flagging this as a known quirk.
- Update 2024-11: decided to go per-package for the threshold check in monorepos. Repo-wide averaging was masking packages that were genuinely underdocumented. Will test this on a couple more projects before considering it settled.
