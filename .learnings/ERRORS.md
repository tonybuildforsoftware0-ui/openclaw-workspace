# ERRORS.md

## 2026-04-27
- Desktop automation blocked by headless server (need Xvfb).

## 2026-05-09
- Python one-liner skill readiness check failed twice due nested f-string/newline quoting inside `python3 -c`; use a single-line list comprehension with simple string concatenation instead.

## 2026-05-12
- `qmd status` printed index status but exited nonzero while trying to build node-llama-cpp Vulkan support because Vulkan libraries/includes/glslc are missing; treat QMD as usable on CPU but avoid assuming a clean zero exit until Vulkan/GPU support is fixed or disabled.

## 2026-05-17
- Tried Gmail/gog auth for `openclawmainemail@agentmail.to`; this failed because AgentMail inboxes are API-first mailboxes, not Google accounts.
- Fix: use AgentMail SDK/API with the saved AgentMail key. Added `scripts/agentmail_monitor.py`, switched `scripts/agentmail_check_cron.sh` to it, and documented the rule in TOOLS.md.
- Next time: for `@agentmail.to`, never start with Gmail OAuth; use the AgentMail API path directly.

## 2026-05-18
- Daily backup push failed because the script built an HTTPS remote from a stale GitHub token source while the active `gh` account on the host was invalid.
- Fix: resolve the token from a live `gh auth token -h github.com -u tony11-cpu` lookup first, then fall back to the saved token file only if needed.

## 2026-05-20
- Daily-maintenance cron failed because the agent tried to run `ps -o pid,ppid,stat,etime,cmd -p 42184 --forest` against a transient tool session id.
- Fix: do not treat OpenClaw tool session ids as OS PIDs; use `pgrep -af` on named processes or wait for the command result instead.

## 2026-05-21
- `gog auth list` failed in a non-interactive shell when the file-backed keyring tried to prompt for its password.
- Fix: when `keyring_backend=file`, set `GOG_KEYRING_PASSWORD` or run with an interactive TTY before using `gog auth list` or other token-reading commands.
