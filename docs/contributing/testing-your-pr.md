# Testing Your PR Locally: OpenHands Contributor Guide

This document explains how contributors and internal engineers should validate changes before pushing and opening a pull request.

Quick checklist
- Run pre-commit hooks and fix all issues
- Run the test suite relevant to your changes (backend, frontend, VSCode extension)
- Optionally smoke-test the full app locally if your change is user-facing
- For UI or agent-behavior changes, attach screenshots/logs and consider an E2E run
- Ensure CI will pass by mirroring the same steps locally

1) Always install and run pre-commit
- One-time install (installs Poetry env and hooks):
  make install-pre-commit-hooks
- Run on staged files (same config CI uses):
  pre-commit run --config ./dev_config/python/.pre-commit-config.yaml
Notes
- If hooks auto-fix files, re-stage and re-run until clean
- Common fixes: Ruff formatting, mypy types, trailing whitespace, EOF newlines

2) Backend changes
- Unit tests (matches CI target):
  poetry run pytest --forked -n auto -svv ./tests/unit
- Runtime tests used by CI:
  TEST_RUNTIME=cli poetry run pytest -svv tests/runtime/test_bash.py
- Full lint on backend (same as CI job "Lint python"):
  pre-commit run --all-files --show-diff-on-failure --config ./dev_config/python/.pre-commit-config.yaml
Suggested when touching core agent logic
- Consider running or requesting an end-to-end/evaluation check (see Section 5)

3) Frontend changes (React app)
- Install and lint/compile/build:
  cd frontend && npm ci && npm run lint && npm run make-i18n && tsc && npm run build && cd ..
- Unit tests with coverage (mirrors CI job "FE Unit Tests"):
  cd frontend && npm run test:coverage && cd ..

4) VSCode extension changes
- In the extension directory:
  cd openhands/integrations/vscode \
  && npm install \
  && npm run lint:fix \
  && npm run typecheck \
  && npm run compile \
  && npm run test \
  && cd ../../..

5) End-to-End (E2E) tests
Run in CI
- Add the "end-to-end" label to your PR to trigger .github/workflows/e2e-tests.yml
Run locally (headless or visible)
- See tests/e2e/README.md for options. Typical quick run:
  cd tests/e2e
  poetry run pytest test_settings.py::test_github_token_configuration test_conversation.py::test_conversation_start -v
- To run with a visible browser:
  poetry run pytest test_settings.py::test_github_token_configuration -v --no-headless --slow-mo=50

6) Optional: Full app smoke test (GUI)
- Build and run locally:
  export INSTALL_DOCKER=0
  export RUNTIME=local
  make build && make run FRONTEND_PORT=12000 FRONTEND_HOST=0.0.0.0 BACKEND_HOST=0.0.0.0
- Verify UI loads at http://localhost:3001 (or the configured FRONTEND_PORT)

7) What CI will run on your PR
- Lint (backend + frontend): .github/workflows/lint.yml
- Python tests: .github/workflows/py-tests.yml
- Frontend unit tests (if frontend changed): .github/workflows/fe-unit-tests.yml
- E2E tests: .github/workflows/e2e-tests.yml when PR has the "end-to-end" label

8) Git best practices
- Prefer staging specific files (git add <file>) over git add .
- Rebase with upstream before pushing: git fetch upstream && git rebase upstream/<branch>
- Ensure pre-commit passes locally before pushing

9) Troubleshooting
- Missing deps: run make build to ensure all deps are installed
- Playwright/E2E issues: see tests/e2e/README.md and check /tmp/openhands-e2e-*.log
- LLM issues: export DEBUG=1 and inspect logs under logs/llm/

References
- Makefile: build, install-pre-commit-hooks, lint targets (Makefile)
- Pre-commit config: dev_config/python/.pre-commit-config.yaml
- Python tests CI: .github/workflows/py-tests.yml
- Frontend tests CI: .github/workflows/fe-unit-tests.yml
- Lint CI: .github/workflows/lint.yml
- E2E tests CI: .github/workflows/e2e-tests.yml
- E2E local usage: tests/e2e/README.md
- Repository instructions provided with this repository clone (see "Repository Instructions" section in task context)
