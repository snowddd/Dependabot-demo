# Dependabot Demo Project

This repository is a **demo project for testing Dependabot version updates**.  
It is intended to demonstrate how Dependabot can automatically check for updates on a specific npm dependency and create Pull Requests (PRs) to a target branch.

---

## 📦 Project Structure

- `package.json` – Contains the npm dependencies.
- `package-lock.json` – Locks the versions for reproducibility.
- `.github/dependabot.yml` – Dependabot configuration file.

> Note: This demo is configured to only track `google-libphonenumber` updates.

---

## ⚙️ Dependabot Configuration

Dependabot is configured to:

- Track **only `google-libphonenumber`**.
- Open PRs to a dedicated testing branch: `fix/QS-622`.
- Run on a schedule (`hourly` for testing, can be changed to `daily` or `weekly` for production).
- Use a commit message prefix: `deps`.

Example configuration snippet:

```yaml
version: 2
updates:
  - package-ecosystem: "npm"
    directory: "/"
    schedule:
      interval: "daily"
    allow:
      - dependency-name: "google-libphonenumber"
    target-branch: "main"
    commit-message:
      prefix: "deps"
    open-pull-requests-limit: 5


