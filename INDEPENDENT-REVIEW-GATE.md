# P0D3 — Owner-authorized technical review and explicit exception

**Scope:** PR #1: manual-only metadata GitHub OIDC/Sigstore attestation.

**Decision 2026-10-23:** The owner explicitly waives separate-human GitHub approvals for this repository's merge and authorizes owner-delegated technical review. This is NOT an independent security review or independent release approval.

## Technical checks
- The attestation workflow triggers only on manual workflow_dispatch, and runs on main in kurokof0/udcc-p0d3-provenance.
- Reviewed SHA256 subject: 4fec50b85a87702d5fc58c93911028835cd83e1d4ab4f808374628bfd548da66.
- Subject asserts deployment_authorized=false, task_execution_authorized=false and live_pass=false.
- Exact GitHub Actions commits are pinned. No Hermes/SARD source, OAuth, PHI, production tasks or live deployments are changed.

## Safeguards retained
- Branch must use pull requests, enforce admins, linear history, conversation resolution, no force-push and no deletion.
- Owner explicitly allows required approvals = 0 for this repository: NO independent reviewer was obtained.
- Merge does NOT authorize triggering GitHub workflow, operating live observers or dispatching any jobs.
- F01/F02/F03 P0D3 live trust findings remain OPEN. Crypto signature of an owner-controlled workflow is not independent authorization.
