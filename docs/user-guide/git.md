# Git Collaboration

This is the first time I will be working with other in the same codebase, and thinking about how this actually will work.  This document is a space for us to update how this works best for us.  

## Branches

Currently cleaning up `clean-main` but will probably rename as `development`

## How to work on your own version of the code

There are various options 
* create your own personal branch -- create a pull request in the development branch when your feature is tested
* create a seperate directory called `/sandbox`.  Make certain your `.gitignore` file contains this folder so that it is not committed back to the repo before you are ready.  

---

# 🤝 Collaboration Guidelines

## Branch Protection Rules

- The `main` branch is **protected**.
- All changes must be made via **Pull Requests (PRs)** — no direct pushes.

## Pull Request Requirements

- Open a PR from your feature branch.
- At least **1 approval** is required before merging.
- All **conversations and review comments must be resolved** before merge.
- If you push new commits after approval, the PR will need a **new approval**.
- Keep your branch **up-to-date with `main`** before merging.

## Merge Methods

- You may **Merge**, **Squash**, or **Rebase** your pull requests, depending on the situation.
- **Squash merging** is encouraged for small, single-purpose changes to keep history clean.

## Admin Policy

- Only repository admins can bypass branch protections when necessary.
- Admins may push directly to `main` in rare cases (e.g., hotfixes).

---

# 🧹 Best Practices

- Name branches clearly (e.g., `feature/add-login`, `fix/typo-readme`).
- Keep PRs focused and small when possible.
- Add a short description to your PR summarizing:
  - What was changed
  - Why the change is needed
  - Any testing or review notes

---

# ✅ Quick PR Template (Optional)

When opening a Pull Request, include:

```markdown
## Summary
- [Short description of the change]

## Testing
- [How you tested it]

## Review
- [Anything reviewers should focus on]
```

---

# 🚀 Thank you for contributing!

---
