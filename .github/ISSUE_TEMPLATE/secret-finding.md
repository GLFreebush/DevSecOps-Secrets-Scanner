---
name: Secret Finding
about: Report a secret or credential detected by GitGuardian secret scanning
title: "🚨 [Secret Scan] <secret-type> detected in <file-path>"
labels: ["security", "secret-detected"]
assignees: GLFreebush
---

## 🚨 Secret Detected

GitGuardian has identified a potential secret or credential exposure in this repository.

---

## Details

| Field | Value |
|---|---|
| **Secret Type** | <!-- e.g. API Key, AWS Credential, Database Password, SSH Private Key, Generic Token --> |
| **File Path** | <!-- e.g. `src/config/database.js` --> |
| **Line Number** | <!-- e.g. Line 42 --> |
| **Branch / Commit** | <!-- e.g. `main` @ `abc1234` --> |
| **Severity Level** | <!-- 🔴 Critical / 🟠 High / 🟡 Medium / 🟢 Low --> |
| **Detected By** | GitGuardian |

---

## Sanitized Reference

> **Do not paste the actual secret here.** Provide only enough context to identify the location.

```
File   : <file-path>
Line   : <line-number>
Hint   : <first 4 chars>****<last 4 chars>  (sanitized)
```

---

## Remediation Recommendations

- [ ] **Immediately invalidate** the exposed credential (rotate key / token / password).
- [ ] **Remove** the secret from the source file and replace it with a reference to a GitHub secret or environment variable.
- [ ] **Purge** the secret from git history using [`git filter-repo`](https://github.com/newren/git-filter-repo) or [BFG Repo Cleaner](https://rtyley.github.io/bfg-repo-cleaner/).
- [ ] **Verify** the fix by re-running the secret scan workflow.
- [ ] **Document** the incident in your security log.

---

## Workflow Run

Link to the workflow run that detected this secret:
<!-- e.g. https://github.com/GLFreebush/DevSecOps-Secrets-Scanner/actions/runs/12345 -->

---

## References

- [GitGuardian Dashboard](https://dashboard.gitguardian.com/)
- [GitHub Encrypted Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets)
- [Removing sensitive data from a repository](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)

> ⚠️ **Do not close this issue until the secret has been fully rotated and removed from history.**
