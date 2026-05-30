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

## 2026-05-30
- `agent-browser network route --body` registered successfully in version 0.27.0 but did not override test `fetch()` responses from `httpbin.org/json` or `example.com/data.json`; `network route --abort` did block matching requests.
- Fix/workaround: use `--abort` for reliable blocking, and verify any mock-body route with console output plus `agent-browser network requests` before relying on it.
- `agent-browser tab 1` / `tab 2` failed because current CLI expects stable tab ids like `t1`/`t2` or labels, not positional integers.
- Fix: run `agent-browser tab list`, then switch with `agent-browser tab t1` or a label.
- Running `openclaw update` from a process descended from the OpenClaw Gateway fails by design because it cannot safely stop/restart its own parent. Running only that update step through `systemd-run` can still kill the parent updater if the parent is inside the Gateway process tree.
- Fix: run the whole updater script from root cron or a detached systemd unit. Do not nest only the update step inside a Gateway-owned script.
- Session-log audit found one JSONL file with leading NUL bytes before a valid JSON object, which made `jq` fail with `Invalid numeric literal`.
- Fix: keep a backup, strip only leading NUL bytes from affected lines, rerun `jq empty` across all session JSONL files, and prefer robust `jq -R fromjson` patterns when scanning raw logs at scale.

## 2026-05-30
- `university_form_automation.py` failed because the Python runtime was missing `beautifulsoup4` and `selenium`.
- Fix: install the missing packages in the user site for the cron/runtime Python, then verify each site path separately because Stony Brook News, Stony Brook Matters, and CCNY no longer share the same form flow.
- `op whoami` failed in a fresh tmux session with `no account found for filter`, so the 1Password CLI is installed but not authenticated in this environment.
