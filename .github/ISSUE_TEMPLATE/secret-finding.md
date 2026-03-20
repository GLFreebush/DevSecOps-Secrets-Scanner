---
name: Secret Finding
about: Report a detected secret or credential exposure
title: '🚨 Secret Detected: [SECRET TYPE] in [FILE PATH]'
labels: security, secret-detected
assignees: GLFreebush
---

## Secret Detection Report

### Repository
<!-- e.g. GLFreebush/DevSecOps-Secrets-Scanner -->

### Secret Type
<!-- Select one: API Key / Token / Password / SSH Key / Certificate / Other -->

### File Location
<!-- Path to the file containing the secret (do NOT include the actual secret value) -->
`path/to/file.ext`

### Line Number(s)
<!-- Approximate line number(s) where the secret was found -->

### Severity Level
<!-- Select one: Critical / High / Medium / Low -->
- [ ] Critical
- [ ] High
- [ ] Medium
- [ ] Low

### Detection Source
<!-- How was this secret found? -->
- [ ] GitGuardian automated scan
- [ ] Manual code review
- [ ] Other security tool

### Sanitized Reference
<!-- A sanitized description of the secret (e.g., "AWS Access Key starting with AKIA...") — do NOT paste the actual secret -->

### Description
<!-- Brief description of what this secret is and its potential impact if exploited -->

---

## Remediation Checklist

- [ ] Immediately invalidate / revoke the exposed credential
- [ ] Generate new replacement credentials
- [ ] Remove the secret from the codebase
- [ ] Purge the secret from git history (use `git filter-repo` or BFG Repo Cleaner if committed)
- [ ] Update all systems that use this credential with the new value
- [ ] Store the new secret securely (GitHub Secrets / secrets manager)
- [ ] Verify no other locations contain the same secret
- [ ] Confirm the old credential is fully deactivated

## Recommended Actions

1. **Rotate immediately** — Go to the service provider and revoke/regenerate the credential.
2. **Remove from code** — Delete the secret from the file and commit the change.
3. **Clean history** — If the secret was ever committed, rewrite git history to remove it.
4. **Audit access logs** — Check whether the exposed credential was used by unauthorized parties.
5. **Document the incident** — Record what happened for future audits.

## References

- [GitGuardian Dashboard](https://dashboard.gitguardian.com/)
- [GitHub Secrets Documentation](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- [Removing Sensitive Data from Git History](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)
- [OWASP Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html)
