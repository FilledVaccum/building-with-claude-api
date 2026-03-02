# Security Policy

## Reporting Security Issues

If you discover a security vulnerability, please report it privately to the repository maintainers.

**Do not report security vulnerabilities through public GitHub issues.**

## Security Best Practices

### API Key Management

This repository contains code examples that interact with the Claude API. Always:

- **Store API keys in environment variables** (e.g., `ANTHROPIC_API_KEY`)
- **Never hardcode API keys** in notebooks or scripts
- **Add `.env` files to `.gitignore`**
- **Rotate keys immediately** if accidentally exposed

### Before Running Code

1. Set up your API key as an environment variable:
   ```bash
   export ANTHROPIC_API_KEY=your-key-here
   ```

2. Or use a `.env` file (which is gitignored):
   ```
   ANTHROPIC_API_KEY=your-key-here
   ```

### Before Committing

1. Review all files: `git status`
2. Check for secrets: `git diff`
3. Clear notebook outputs if they contain sensitive data
4. Verify `.gitignore` is working

### If You Accidentally Commit Secrets

1. **Immediately revoke/rotate the exposed credentials**
2. Remove from git history using `git filter-branch` or BFG Repo-Cleaner
3. Force push to remote
4. Consider the key permanently compromised

## Dependencies

Keep Python packages updated:
```bash
pip list --outdated
pip install --upgrade <package-name>
```
