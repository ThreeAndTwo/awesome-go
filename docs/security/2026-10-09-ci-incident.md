# CI security incident — 2026-10-09

Repository: `ThreeAndTwo/awesome-go`
Branch: `main`
Head inspected before this change: `f211a2c9543bf4507497a1341416e5f77649279a`

Unauthorized GitHub Actions workflows were identified during an owner-requested review.
The reviewed workflows attempted to send repository/history data or GitHub Actions secrets to an unapproved external endpoint.
Do not restore or execute these workflows. A successful Actions run alone does not establish which credentials were received or remained valid.

The known malicious workflow is absent from this branch at the inspected head; this commit adds the cleanup record.

Review and containment notes

- Keep legitimate build/test/release workflows; suspicious names alone are not evidence.
- Revoke or rotate credentials that may have been exposed; deleting a workflow or a GitHub Secret does not revoke credentials at their issuing service.
- Historical commits are retained for evidence. This change does not rewrite Git history.
- The initial credential compromise remains under investigation; this record does not attribute it to a person or tool.
