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

> **DISCLAIMER** Below was written by ChatGPT.  I did ask it to be friendly and warm! :-D  

## Working Together

To help us keep the project organized and high-quality, we follow a few lightweight practices:

- The `main` branch is **protected** to ensure stable and reliable code.
- Changes should come through **Pull Requests (PRs)** — it's the best way to review and improve together.
- Direct pushes to `main` are restricted to keep history clean and traceable.

---

## Opening Pull Requests

When opening a PR:

- Start from a feature branch.
- One **peer approval** is encouraged before merging.
- Please resolve any open review comments or conversations.
- If new commits are added after approval, a quick re-approval helps keep reviews up to date.
- Keep your branch **in sync with `main`** to avoid conflicts.

---

## Merging Options

You are free to choose the merge method that fits best:

- **Merge**, **Squash**, or **Rebase** are all supported.
- **Squash merging** is recommended for small or self-contained changes to keep commit history tidy.

---

## Stewardship

- Admins help guide the project and can bypass branch protections if necessary.
- Day-to-day contributions, reviews, and merges are open and collaborative.

---

# 🧹 Best Practices

- Name branches clearly (e.g., `feature/login-page`, `fix/readme-typo`).
- Try to keep PRs focused on a single topic or improvement.
- Include a short description in your PR:
  - What was changed
  - Why it was needed
  - How it was tested

---

# ✅ Quick Pull Request Template (Optional)

When opening a Pull Request, feel free to use:

```markdown
## Summary
- [What does this change do?]

## Testing
- [How was this verified?]

## Review
- [Anything specific you'd like reviewers to focus on?]
```

---

# 🚀 Thank you for contributing and helping the project grow!

---


