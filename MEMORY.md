# MEMORY - Long-Term Intelligence Log

## Decisions Made
- *[2026-04-19]* - Updated Mega's role definition to final version: 60% school/college focus, 40% general research/deep thinking. Strict routing rules: coding/technical → Volt; school/research/deep thinking → Mega; simple tasks → Oboz.
- *[2026-05-20]* - Tony created/added Oboz to a group called "Knowledge base (RAG)" (\`telegram:-1003865331229\`) that is only for Tony and Oboz. Treat it as Tony's personal memory/RAG inbox: when Tony posts discoveries, notes, reminders, or things he wants retained there, capture/save them into the appropriate memory/knowledge files. Keep responses minimal but acknowledge when useful; this is not a public group and should not be treated like casual group chat.
- *[2026-05-23]* - For NYC tech/events networking, Tony wants intros that are honest and builder-focused: mention he is a high school student in NYC, say he builds automation/tools, and ask practical learning questions. Keep it natural, humble, and not overly polished or fake.

## Optimizations Discovered
- *[2026-04-19]* - Renamed coding agent from codywoody to Volt across all configs.

## Failed Approaches
- *[2026-04-21]* - Repeatedly asking user for email instead of using configured Zapier MCP connection. Failed to properly automate morning briefs and heartbeats. User frustration escalated after multiple reminders.

## System Upgrades
- *[2026-05-20]* – **Stale hashed dist chunk repair**: OpenClaw cron jobs began failing with `ERR_MODULE_NOT_FOUND` for old hashed bundle paths (`run-session-state-CCT9Dyo2.js` and `plugins-DJit8KgP.js`) after the installed dist tree had already moved on to newer chunk names. Repaired the live gateway non-disruptively by adding compatibility symlinks from the old names to the current files and verified both paths import successfully. If this recurs after an update, check for stale hashed dist references before forcing a gateway restart.
- *[2026-05-20]* – **Daily maintenance auto-heal upgraded**: Replaced `scripts/daily-maintenance.sh` with a safer auto-heal script that checks services, disk, OpenClaw update status, security audit, Telegraf metrics, Uptime Kuma, Traefik, Dozzle, and recent container logs. Added root cron at 03:30 America/New_York with `AUTO_UPDATE=1` so OpenClaw updates run outside the gateway process tree. The script now runs a safety gate before updates, records pre-change snapshots under `memory/maintenance/prechange-*`, applies targeted fixes, retries after diagnostics, and verifies post-change OpenClaw health. Updated the OpenClaw `daily-maintenance` cron to run at 04:00 as a review/report/follow-up pass: read host logs, run `AUTO_UPDATE=0` verification, learn from failures, apply one targeted safe fix, retry, and report remaining blockers. Risky changes still require reporting instead of blind execution.
- *[2026-05-21]* – **Gmail OAuth architecture mapped**: Confirmed OpenClaw’s primary Gmail access is handled by `gog`, not the OpenClaw Google plugin. OAuth client credentials live in `~/.config/gogcli/credentials.json`; refresh tokens are stored in the encrypted file keyring under `~/.config/gogcli/keyring/` when `keyring_backend=file`. The existing main account is `tony.guirguis.dell@gmail.com`. Multi-account separation is handled by `--account`/`GOG_ACCOUNT` for account targeting and `--client`/`GOG_CLIENT` for isolated OAuth client buckets. For a second Gmail account, keep the existing client intact, add a separate read-only Gmail token, and do not reuse AgentMail credentials.
- *[2026-05-21]* – **College Gmail + main Gmail stabilized**: Added a dedicated `college` OAuth client bucket for `tonymasoudnyc@gmail.com`, kept the main mailbox on the `default` bucket for `tony.guirguis.dell@gmail.com`, and verified both accounts with live `gog gmail search`. To make headless reads work consistently, `gog` now runs through a wrapper that exports an empty `GOG_KEYRING_PASSWORD`, and the canonical config files/TOOLS.md were updated to reflect the `default` + `college` split.
- *[2026-05-21]* – **Dead group cron cleanup / restore**: Removed stale Telegram cron jobs that still pointed at deleted group targets (`skill-vetter-monthly`, `second-gmail-oauth-reminder-2026-05-21-1530`, and both `bigfuture-40k-reminder-*` jobs), then restored the reminder jobs after Tony said he still needed them. `nyssb-weekly-reminder` was repaired to send to the live Knowledge Base (RAG) group at `telegram:-1003865331229` instead of leaving it targetless.
- *[2026-05-21]* – **Git Essentials installed**: Installed ClawHub skill `git-essentials` into `/root/.openclaw/workspace/skills/git-essentials`. It is the canonical Git reference for repo/deployment work; execute with native `git` commands and use the skill as the instruction layer.
- *[2026-04-19]* – Added Zapier MCP integration for Gmail, YouTube, Google Docs, Drive, and 4000+ apps. Token saved in `/root/.openclaw/credentials/zapier-mcp.json`. Documented in TOOLS.md.
- *[2026-04-21]* – Fixed morning brief automation: Created cron job (`*/30 * * * * /usr/bin/openclaw heartbeat`), added morning brief script, and automated 9 AM Eastern tech/AI/college briefing delivery. Email checks now use Zapier MCP without user prompting.
- *[2026-04-27]* – **AgentMail Integration**: Configured dedicated email `openclawmainemail@agentmail.to` for college/scholarship monitoring. API key documented in TOOLS.md. Sent subscription requests to Stony Brook University (`news@stonybrook.edu`, `alumni@stonybrook.edu`) and City College of NY (`admissions@ccny.cuny.edu`, `graduateadmissions@ccny.cuny.edu`). Note: `cunynews@cuny.edu` blocks automated emails. Desktop automation tools (PyAutoGUI) installed for future web form submissions.
- *[2026-04-27]* – **AgentMail Automation Complete**: Implemented 6-hour inbox check cron job, webhook security with allowlist (code ready), self‑improvement activation (.learnings directory), and headless web form automation (Xvfb, Selenium). All configurations documented in TOOLS.md and SUBAGENT_SETUP.md. Subscription confirmations already detected from graduateadmissions@ccny.cuny.edu.
- *[2026-05-12]* – **Daily backup auto-allowed**: Updated the daily backup cron to call `/root/.openclaw/workspace/scripts/daily-backup.sh` directly and added a host exec allowlist entry for that script, so backup runs can proceed without manual approval prompts while keeping the trust scope narrow.
- *[2026-05-12]* – **Scholarship source stack added**: Tony provided Fastweb, Naviance, Sallie merit scholarships, NY HESC/Excelsior, Niche, College Board BigFuture, Scholarships360 weird scholarships, and CareerOneStop as recurring scholarship sources. Updated TOOLS.md, Mega's AGENTS.md, root AGENTS.md, and `memory/scholarship-sources.md`; updated daily brief cron to run as Mega and added a weekly Mega scholarship sweep.
- *[2026-05-12]* – **Daily brief scholarship/STEM optimization**: Tony clarified he is currently a high-school junior with a strong/very good GPA, wants NYC as the default location, and wants daily briefs to include (1) best-fit scholarships from his source stack and (2) NYC-area university/college tech, STEM, coding, software, engineering, internship, course, or pre-college opportunities that improve skill and CV before college. Keep matching general until more profile data exists and keep scans credit-efficient. For every scholarship recommendation, include a compact plan covering requirements, materials needed, application path, preparation order, and next steps to improve Tony's chance.
- *[2026-05-13]* – **Direct Gmail monitoring connected**: Set up Gmail OAuth on the VPS with `gog`, resolved the keyring backend to file mode, and verified live Gmail access by reading Tony's mailbox (`tony.guirguis.dell@gmail.com`) from the VPS. Latest successful read returned Security alert, LinkedIn News, BigFuture School, Rowan University Admissions, and Quinnipiac University mail. Added a 4-hour Gmail monitor cron in OpenClaw that will read new mail, keep an empty-run message short, research scholarship/opportunity mentions, and stay compact/safe.
- *[2026-05-14]* – Tony wants the assistant to work silently by default and avoid avoidable approval prompts. Prefer safe first-class tools, batch actions, and only surface approvals when OpenClaw truly requires them.
- *[2026-05-14]* – Tony wants even less interruption: keep replies short, don’t ask for confirmation unless the action is truly blocked, and take the safe next step immediately.
- *[2026-05-15]* – Tightened the 4-hour Gmail monitor cron to explicitly avoid forwarding `/approve` permission commands, use the saved Gmail state file for deltas, and stay on the already-authorized Gmail path instead of falling back to noisy prompts.
- *[2026-05-15]* – Cleaned up the daily backup script so cron delivery handles notifications, while the script itself stays quiet and only reports real blockers; backup failure root cause was GitHub push protection blocking `scripts/send_college_subscriptions.py` secrets in an older backup path.
- *[2026-05-18]* – **Telegraf native VPS monitoring integrated**: Consolidated Telegraf onto the host `telegraf.service`, stopped and disabled restart for the older `openclaw-telegraf` Docker collector, added `systemd_units`, support-process `procstat`, and `/usr/local/bin/openclaw-automation-metrics` via narrow sudoers for service/container/cron/log freshness metrics. Updated `HEARTBEAT.md` and the daily-maintenance OpenClaw cron to use `openclaw-telegraf-metrics summary|automation` as the first VPS health source.
- *[2026-05-20]* – **Daily-maintenance cron hardening**: The maintenance agent briefly failed because it tried to `ps` its own transient tool session id (`42184`) as if it were a real OS PID. Added a guard to the `daily-maintenance` cron prompt forbidding `ps` on OpenClaw session ids and steering process checks to named-process probes like `pgrep -af`.
- *[2026-05-20]* - NYC_T shared a world-language culminating project sheet that appears to be for the New York State Seal of Biliteracy (NYSSB). He wants help finishing it by summer, wants a weekly reminder in the Knowledge Base (RAG) group until then, and said he is taking Arabic for the project.

### Subscription Confirmations (2026-04-27)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- openclawmainemail@agentmail.to: Newsletter Subscription Request: City College Graduate Admissions
- openclawmainemail@agentmail.to: Newsletter Subscription Request: City College Admissions
- openclawmainemail@agentmail.to: Newsletter Subscription Request: Stony Brook University Alumni
- openclawmainemail@agentmail.to: Newsletter Subscription Request: Stony Brook University News
- openclawmainemail@agentmail.to: Newsletter Subscription Request: City College Graduate Admissions
- openclawmainemail@agentmail.to: Newsletter Subscription Request: City College Admissions
- openclawmainemail@agentmail.to: Newsletter Subscription Request: Stony Brook University Alumni
- openclawmainemail@agentmail.to: Newsletter Subscription Request: Stony Brook University News
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates
- openclawmainemail@agentmail.to: Test AgentMail Subscription
- openclawmainemail@agentmail.to: Subscription Request: City College Graduate Admissions
- openclawmainemail@agentmail.to: Subscription Request: City College Admissions
- openclawmainemail@agentmail.to: Subscription Request: City College of New York News
- openclawmainemail@agentmail.to: Subscription Request: Stony Brook University Alumni
- openclawmainemail@agentmail.to: Subscription Request: Stony Brook University News
- openclawmainemail@agentmail.to: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-04-27)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-04)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-06)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-06)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-06)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-07)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates

### Subscription Confirmations (2026-05-17)
- graduateadmissions@ccny.cuny.edu: Automatic reply: [EXTERNAL] Newsletter Subscription Request: City College Graduate Admissions
- mailer-daemon@amazonses.com: Undeliverable: Subscription Request: SUNY Updates
