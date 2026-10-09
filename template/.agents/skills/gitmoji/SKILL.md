---
name: gitmoji
description: Use Gitmoji to write clear, consistent Git commit messages.
---

# Gitmoji commit messages

Use Gitmoji when proposing or writing commit messages for this project. Prefix the subject with one emoji that communicates the primary intent of the change.

## Format

`<emoji> <imperative summary>`

Examples:

- `✨ Add account recovery flow`
- `🐛 Fix token refresh race condition`
- `📝 Document local development setup`
- `♻️ Refactor request validation`
- `✅ Add tests for expired sessions`
- `🔒 Validate authorization before returning records`
- `🔥 Remove deprecated configuration path`
- `🚀 Improve startup performance`
- `🧪 Add regression test for empty input`
- `🔧 Update development tooling configuration`
- `⬆️ Upgrade dependency versions`
- `👷 Fix continuous integration workflow`

## Choosing an emoji

Choose the emoji by the primary purpose of the change, not by every file touched. Prefer the established Gitmoji convention and use the same meaning consistently across commits.

Common choices:

| Emoji | Intent |
|---|---|
| ✨ | Introduce a feature |
| 🐛 | Fix a bug |
| 📝 | Documentation-only change |
| ♻️ | Refactor without intended behavior change |
| ✅ | Add or update tests |
| 🔒 | Security or privacy improvement |
| 🚀 | Performance improvement |
| 🧪 | Add or adjust tests/experiments |
| 🔧 | Configuration or tooling |
| ⬆️ | Upgrade dependencies |
| 👷 | CI/build system work |
| 🔥 | Remove code or files |
| 💄 | UI or styling changes |
| 🌐 | Internationalization or localization |
| ⚡️ | Improve performance in a focused way |
| 🚑 | Critical hotfix |

## Rules

- Keep the subject concise and specific.
- Use imperative wording after the emoji, such as `✨ Add ...` or `🐛 Fix ...`.
- Do not choose an emoji that overstates the impact or purpose.
- Do not invent a new emoji mapping when an established one fits.
- If the repository has a more specific commit-message policy, follow it and keep this skill consistent with it.
- When asked to create a commit, inspect the staged diff first and choose the emoji based on the actual change. Never commit unless the user or the active workflow authorizes committing.
- This skill governs commit-message conventions; it does not authorize making commits or pushing changes by itself.
