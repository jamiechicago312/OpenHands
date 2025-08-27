# Bug Report Template (OpenHands)

Use this template to file Issues so maintainers can reproduce quickly.

Title
- [Bug]: Short, specific description

Checklist
- [ ] I searched existing issues and didn’t find a duplicate
- [ ] I can reproduce consistently using the steps below

Environment
- How you run OpenHands: Docker command from README | GitHub resolver | Development workflow | CLI | app.all-hands.dev | Other
- OS: macOS | Linux | WSL on Windows (and version)
- OpenHands version: e.g., 0.42.0, main, commit SHA
- Model provider/name: e.g., gpt-4o, claude-3-5-sonnet, openrouter/deepseek-r1
- Relevant env/config: e.g., LLM_BASE_URL, runtime, custom settings

Description
- What happened vs. what you expected to happen

Reproduction steps (exact, numbered)
1. Step-by-step actions, including prompts/commands, repo used, files edited
2. Include minimal example when possible

Observed behavior
- Logs, stack traces, errors, screenshots
- For UI bugs, include before/after screenshots and browser console logs if applicable
- If you’re using the UI, consider sharing a conversation link (thumbs-down in the UI provides a shareable link)

Additional context
- Any recent changes, network constraints, proxies, etc.

Attachments
- LLM logs: see logs/llm/default
- E2E/local logs: /tmp/openhands-e2e-*.log if you ran E2E flows

References
- .github/ISSUE_TEMPLATE/bug_template.yml
