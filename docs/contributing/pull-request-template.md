# Pull Request Template (OpenHands)

Please copy this template when opening a PR. For examples of excellent PRs, see recent PRs by @xingyaoww and @neubig.

- [ ] This change is worth documenting at https://docs.all-hands.dev/
- [ ] Include this change in the Release Notes. If checked, provide an end-user friendly description below

End-user friendly description
- What does a user gain or what problem is fixed? Keep this non-technical and concise.

Summary
- What does the PR do? Highlight non-trivial design decisions and trade-offs.
- Scope of change (backend/frontend/VSCode extension/docs)
- Any follow-ups or flags for reviewers

Implementation notes
- Key files changed and why
- Any migrations or config changes
- Feature flags or environment variables

Testing done
- Pre-commit run locally and passing
- Unit tests added/updated and passing
- Frontend build/tests passing (if applicable)
- Any E2E validation (link to run or screenshots if relevant)

Risk assessment and rollout
- Risk level (low/medium/high)
- Backward compatibility considerations
- Rollout plan (e.g., behind a flag) and monitoring/logs to watch

Linked issues and context
- Closes #<issue-id>
- Related to #<issue-ids>

Screenshots or recordings (if UI change)
- Before/after images or short video

Checklist
- [ ] Code follows repo style and conventions
- [ ] Pre-commit hooks pass locally
- [ ] Tests added/updated
- [ ] Docs added/updated (if needed)

References
- .github/pull_request_template.md for required checkboxes used by CI
- Examples:
  - https://github.com/All-Hands-AI/OpenHands/pull/10578 (author: @xingyaoww)
  - https://github.com/All-Hands-AI/OpenHands/pull/10606 (author: @neubig)
