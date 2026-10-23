# P0D3 — Independent Review Gate (not yet approved)

This pull request proposes a **manual-only** GitHub Actions workflow to create an OIDC/Sigstore attestation for the *metadata subject*, not for deployable binaries or operational code.

Reviewed subject SHA256: `4fec50b85a87702d5fc58c93911028835cd83e1d4ab4f808374628bfd548da66`.

## Mandatory before merging or manually running

- A reviewer **other than** `kurokof0` must inspect this PR and approve under the protected `main` branch rule.
- Reviewer must verify the action SHA pins, subject digest, permissions, absence of secrets, and no production code/PHI.
- Commit changes must stay under an approved pull request; no direct pushes to `main`.
- Manual workflow run requires a separately reviewed decision; never treat the result as authorization to deploy.
- Verify the actual GitHub attestation via `gh attestation verify P0D3-RELEASE-EVIDENCE.json --repo kurokof0/udcc-p0d3-provenance --signer-workflow .github/workflows/p0d3-attest.yml`.
- Private keys, OAuth tokens, SARD repositories, release Gate, Hermes Bridge and Windows Scheduled Tasks are all out of scope.
- The signing service authenticates the *workflow identity*; it is not an independent review of the P0D3 runtime or a live login/snapshot proof.
- The repository owner can still change protection settings, so a technically independent human authority or organization policy is not fully established merely by GitHub branch protection.

**Current decision:** signing not performed; independent reviewer not assigned; P0D3 deployment/jobs remain **NO-GO**.
