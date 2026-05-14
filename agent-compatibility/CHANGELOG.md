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
