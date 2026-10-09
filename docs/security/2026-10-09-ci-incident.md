# CI incident containment — 2026-10-09

Repository: `ThreeAndTwo/awesome-go`
Branch: `revert-4080-remove_damsel`
Inspected head: `50001b291772d0d8ad37fe82f0623e5bde05495f`

Actions were disabled before this cleanup. Keep them disabled until the repository owner explicitly approves restoration.

The owner confirmed that this personal repository must not contain GitHub Actions workflows. This change removes every file under `.github/workflows` on this branch, regardless of its name.

Files removed in this change:

- `.github/workflows/run-check.yaml` — original Git object `d17ad7a16bfd32d5e5ae8df20f0b80e63fa7bb9d`.
- `.github/workflows/site-deploy.yaml` — original Git object `bc7a2e56ab6bcda35717b91652cbd1acfdbc3fa2`.
- `.github/workflows/stale.yml` — original Git object `96776191fdfd3472c49bf3d744b41ab06cd82f08`.
- `.github/workflows/tests.yaml` — original Git object `de83e3b63a1f948bbfeff427790d0f2f8a81c34f`.

Evidence and limits

- Unauthorized workflows were observed attempting credential or repository-history disclosure. A successful workflow run alone does not prove data receipt or credential validity.
- Existing Git history is retained as evidence. No release, tag, force push, or history rewrite is part of this cleanup.
- Revoking a GitHub token does not rotate credentials issued by other services.
- The initial credential compromise and the authentication method used for the mass write remain under investigation.
- This record supersedes any earlier note suggesting that personal-repository workflows should be retained.
