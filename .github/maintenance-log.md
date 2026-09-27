# Maintenance log

## 2026-09-27 — Pull-request Windows validation

- **Rationale:** The Windows native checks and application test suite previously ran only after changes reached `main`, so pull requests could merge without project-specific validation.
- **Files changed:** `.github/workflows/build-all.yml` and `.github/maintenance-log.md`.
- **Validation:** Workflow structure review, trigger/condition assertions, YAML parsing, and `git diff --check`. The pull request run provides the authoritative Windows, Node.js 26, native-helper, extension-build, and test validation.
- **Risk:** Low. Existing `main` and manual runs still build and upload installers; pull requests run validation only and retain read-only repository permissions.
- **Rollback:** Revert the maintenance commit to restore post-merge-only Windows validation.
