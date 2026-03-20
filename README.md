# DevSecOps-Secrets-Scanner
Scanning for secrets.
# DevSecOps Secrets Scanner

Automated secret scanning using GitGuardian for GitHub repositories. Detects API keys, tokens, credentials, database passwords, SSH keys, and other sensitive information.

## Features

- ✅ Scans repositories for secrets and sensitive data
- ✅ Automatic issue creation with detailed findings
- ✅ GitHub notifications for identified secrets
- ✅ Email notifications with remediation guidance
- ✅ Runs on push, pull requests, and daily schedule
- ✅ Scans multiple repositories (GLFreebush/Brute-Force-Detection-Engine and GLFreebush/DevSecOps-Secrets-Scanner)

## Prerequisites

- GitHub account with repository access
- GitGuardian account and API key
- GitHub Actions enabled

## Setup Instructions

### 1. Get GitGuardian API Key

1. Go to https://dashboard.gitguardian.com/
2. Sign up or log in
3. Navigate to **Settings > API Keys**
4. Create a new API key and copy it

### 2. Add Secrets to GitHub

1. Go to your repository settings: `Settings > Secrets and variables > Actions`
2. Click **"New repository secret"**
3. Add the following secrets:
   - **Name:** `GITGUARDIAN_API_KEY` | **Value:** (your GitGuardian API key)
   - **Name:** `NOTIFICATION_EMAIL` | **Value:** (your email for alerts)

### 3. Enable GitHub Actions

1. Go to **Settings > Actions > General**
2. Ensure "Allow all actions and reusable workflows" is selected
3. Click **Save**

## How It Works

### Scanning Triggers

- **On Push:** Every commit to any branch triggers a scan
- **On Pull Request:** Every PR submission is scanned
- **Daily Schedule:** Runs at 2:00 AM UTC daily for comprehensive scanning

### Issue Creation

When secrets are detected, an automated issue is created with:
- **Secret Type:** API keys, tokens, passwords, SSH keys, etc.
- **File Location:** Exact file path where secret was found
- **Severity Level:** Critical/High/Medium/Low
- **Line Number:** Specific line containing the secret
- **Remediation Steps:** Recommended actions to take

### Notifications

- **GitHub Issues:** Primary notification method (you'll be notified in-repo)
- **Email:** Summary alerts sent to configured email address

## Monitored Repositories

This action scans:
- `GLFreebush/Brute-Force-Detection-Engine`
- `GLFreebush/DevSecOps-Secrets-Scanner`

## Remediation Workflow

1. **Issue Created:** Automated secret detection alerts
2. **Review:** Check issue details and severity
3. **Rotate:** Invalidate/rotate the exposed secret immediately
4. **Fix:** Remove secret from code and commit history
5. **Close:** Verify fix and close issue

### Important: Rotating Exposed Secrets

If a secret is exposed:
1. **Immediately invalidate** the exposed credential
2. **Generate new credentials** (new API key, token, etc.)
3. **Remove from code** and update with new secret
4. **Scan history** to ensure no other exposures exist
5. **Document incident** for audit purposes

## Best Practices

- ✅ Use GitHub Secrets for storing sensitive data
- ✅ Never commit secrets to repositories
- ✅ Rotate secrets regularly
- ✅ Review scan results promptly
- ✅ Monitor email and GitHub notifications
- ✅ Keep GitGuardian API key secure

## Troubleshooting

### Action Not Running?
- Check **Actions** tab to see workflow status
- Verify API key is correctly set in repository secrets
- Ensure GitHub Actions are enabled in settings

### No Issues Being Created?
- Verify GitGuardian API key is valid
- Check workflow logs for errors
- Ensure notification email is configured

### Missing Scans?
- Verify scan schedule and triggers are configured
- Check repository permissions
- Review workflow file for syntax errors

## Support & Documentation

- [GitGuardian Documentation](https://docs.gitguardian.com/)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [GitHub Secrets Management](https://docs.github.com/en/actions/security-guides/encrypted-secrets)

## License

[Your License Here]

## Contact

For questions or issues, contact: @GLFreebush
