# OpenHands Bug Report

Analysis of the most recent 200 open issues in the OpenHands/OpenHands repository.

## Top 10 Bug Patterns (by frequency)

### 1. Error Crash (16 issues)

**Examples:**
- **#11543**: [Bug]: Hard Crash when model tries to use unsupported parameters for execute_bash
  - URL: https://github.com/OpenHands/OpenHands/issues/11543
  - Labels: bug
- **#11472**: [Bug]: Github resolver fails with opaque error when lacking permissions
  - URL: https://github.com/OpenHands/OpenHands/issues/11472
  - Labels: bug, openhands
- **#11451**: [Bug]: module 'openhands' has no attribute '__version__' when running SWE-Bench evaluation due to source not linked in Poetry environment
  - URL: https://github.com/OpenHands/OpenHands/issues/11451
  - Labels: bug, evaluation
  - ... and 13 more issues

### 2. Installation (14 issues)

**Examples:**
- **#11512**: [Bug]: There is no docker.all-hands.dev/openhands/runtime
  - URL: https://github.com/OpenHands/OpenHands/issues/11512
  - Labels: bug, OH repository, reproduced
- **#11501**: [Bug]: Directory permission issue persists in v0.59 - agent creates directories with root uid/gid
  - URL: https://github.com/OpenHands/OpenHands/issues/11501
  - Labels: bug
- **#11491**: [Bug]: convert_tools_to_description does not parse nested parameters of tools
  - URL: https://github.com/OpenHands/OpenHands/issues/11491
  - Labels: bug
  - ... and 11 more issues

### 3. Llm Model (11 issues)

**Examples:**
- **#11552**: [Bug]: Default `reasoning_effort='high'` causes 400 errors with OpenAI Responses API models for unverified organizations
  - URL: https://github.com/OpenHands/OpenHands/issues/11552
  - Labels: bug
- **#11498**: [Bug]: BadRequestError: litellm.BadRequestError: OpenAIException - { "error": { "message": "Unsupported parameter: 'temperature' is not supported with this model.", "type": "invalid_request_error", "param": "temperature", "code": null } }
  - URL: https://github.com/OpenHands/OpenHands/issues/11498
  - Labels: bug, llm
- **#11433**: [Bug]: Unsupported parameter: 'stop' when using GPT-5 provided by Azure
  - URL: https://github.com/OpenHands/OpenHands/issues/11433
  - Labels: bug, llm
  - ... and 8 more issues

### 4. Cli Terminal (8 issues)

**Examples:**
- **#11482**: [Bug]: openhands cli freezes when running bash-tool
  - URL: https://github.com/OpenHands/OpenHands/issues/11482
  - Labels: bug, CLI
- **#11361**: [Bug]: selected text in the terminal tab does not show up as highlighted
  - URL: https://github.com/OpenHands/OpenHands/issues/11361
  - Labels: bug, terminal/commands, OH UI/UX
- **#11180**: [Bug]: "Unmatched ( or \(" errors when running `grep` commands
  - URL: https://github.com/OpenHands/OpenHands/issues/11180
  - Labels: bug, agent quality, agent
  - ... and 5 more issues

### 5. Api Integration (6 issues)

**Examples:**
- **#11330**: use github copilot in local litellm
  - URL: https://github.com/OpenHands/OpenHands/issues/11330
  - Labels: bug, llm
- **#11306**: [Bug]: Bitbucket integration no longer works when running OpenHands locally
  - URL: https://github.com/OpenHands/OpenHands/issues/11306
  - Labels: bug, git Integrations, bitbucket
- **#11253**: [Bug]: Agent got stuck in condensation loop. Can able to chat.
  - URL: https://github.com/OpenHands/OpenHands/issues/11253
  - Labels: bug, condenser
  - ... and 3 more issues

### 6. Feature Request (3 issues)

**Examples:**
- **#11483**: [Bug]: [CLI V1]: User microagents from ~/.openhands/microagents/ not loaded in openhands-cli
  - URL: https://github.com/OpenHands/OpenHands/issues/11483
  - Labels: bug, CLI
- **#11461**: macOS: "openhands-macos" cannot be opened - Apple Gatekeeper security issue
  - URL: https://github.com/OpenHands/OpenHands/issues/11461
  - Labels: bug, CLI
- **#11344**: [Bug]: Hard to read CLI outputs on light themed terminal
  - URL: https://github.com/OpenHands/OpenHands/issues/11344
  - Labels: bug, CLI

### 7. Workspace (3 issues)

**Examples:**
- **#11308**: [Bug]: OpenHands Provider Qwen 3 Coder provides incoherent results
  - URL: https://github.com/OpenHands/OpenHands/issues/11308
  - Labels: bug, llm
- **#11206**: [Bug]: Locally mounted folders are chowned to root
  - URL: https://github.com/OpenHands/OpenHands/issues/11206
  - Labels: bug
- **#11109**: [Bug]: evaluation/benchmarks/swe_bench/run_infer.py  initialize_runtime with run 'which python' error occasionally
  - URL: https://github.com/OpenHands/OpenHands/issues/11109
  - Labels: bug, evaluation

### 8. Agent Behavior (2 issues)

**Examples:**
- **#11432**: [Bug]: Deadlock after TaskTrackingAction in headless mode
  - URL: https://github.com/OpenHands/OpenHands/issues/11432
  - Labels: bug, llm
- **#11012**: [Bug]: ripgrep options in ReadOnlyAgent
  - URL: https://github.com/OpenHands/OpenHands/issues/11012
  - Labels: bug, Stale, agent

### 9. Ui Frontend (2 issues)

**Examples:**
- **#11057**: [Bug]: Text in main message input box disappears on redraw (repository-selection-form)
  - URL: https://github.com/OpenHands/OpenHands/issues/11057
  - Labels: bug, OH UI/UX, app-team
- **#11056**: [Bug]: Messages are lost when server is stopped and status indicator is unclear
  - URL: https://github.com/OpenHands/OpenHands/issues/11056
  - Labels: bug, OH UI/UX, backend

