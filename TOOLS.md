# TOOLS.md - Local Notes

Skills define _how_ tools work. This file is for _your_ specifics — the stuff that's unique to your setup.

## What Goes Here

Things like:

- Camera names and locations
- SSH hosts and aliases
- Preferred voices for TTS
- Speaker/room names
- Device nicknames
- Anything environment-specific

## Examples

```markdown
### Cameras

- living-room → Main area, 180° wide angle
- front-door → Entrance, motion-triggered

### SSH

- home-server → 192.168.1.100, user: admin

### TTS

- Preferred voice: "Nova" (warm, slightly British)
- Default speaker: Kitchen HomePod
```

### Zapier MCP ⚡️
- **Connected:** 2026-04-19
- **Token:** `/root/.openclaw/credentials/zapier-mcp.json`
- **Capabilities:**
  - 📄 **Docs** – Create/edit Google Docs, generate reports
  - ▶️ **YouTube** – Search videos, get metadata
  - 📁 **Google Drive** – Read/write files, manage folders
  - 🔄 **4000+ apps** – Any Zapier-connected service

**Morning Brief Setup:**
- **Tech/AI/Colleges brief** – Runs daily at 09:00 EST via cron
- **Email check** – Auto-fetches via Agentmail API Key (no prompting)
- **Cron configured:** `*/30 * * * * /usr/bin/openclaw heartbeat`

**Remember: Use Zapier MCP for:**
- Cross-app automation (docs + drive)
- YouTube research and video metadata
  - Gmail compose/search - Use this instead of asking for email!
- File management in Drive

## Why Separate?

Skills are shared. Your setup is yours. Keeping them apart means you can update skills without losing your notes, and share skills without leaking your infrastructure.

---

Add whatever helps you do your job. This is your cheat sheet.

### College Monitoring Gmail 🎓 (Dedicated Account - IMAP ACCESS)
- **Access Method:** Agentmail API Key "[AGENTMAIL_API_KEY]"
- **Purpose:** College/scholarship monitoring for NY universities
- **Monitoring Targets:**
  - Scholarships in New York (merit-based, need-based)
  - NYU, Columbia, CUNY, SUNY admissions updates
  - Application deadlines & requirements
  - Extracurricular opportunities for college apps
  - High school to college transition programs

**Use this for:**
- College opportunity monitoring (every 6h cron)
- Scholarship deadline tracking (daily digest 8pm)
- University email subscriptions (NY-focused)
- All education-related email automation

**Auth rule:** `openclawmainemail@agentmail.to` is an AgentMail API inbox, not a Gmail/Google account. Do **not** try to authorize it with `gog`; use the AgentMail API key and `scripts/agentmail_monitor.py`.

**Security Notes:**
- Credentials stored securely (root only)
- Use for college/scholarship tasks only
- No personal data in this account
- Operational resource for college goals
- IMAP access only - no OAuth setup needed

### QMD Hybrid Search Engine 🔍
- **Installed:** 2026-04-26
- **Binary:** `/usr/bin/qmd` (version 2.1.0)
- **Cache location:** `~/.cache/qmd/`
- **Index location:** `~/.cache/qmd/index.sqlite`
- **Models (downloaded):** `~/.cache/qmd/models/` (embeddinggemma-300M, qmd-query-expansion-1.7B, Qwen3-Reranker-0.6B pending)
- **Collection:** `openclaw` (covers workspace)
- **Context:** Global and collection-specific added

**Use this for:**
- Finding any local file before asking the user
- Searching across all workspace markdown files (SOUL.md, AGENTS.md, TOOLS.md, HEARTBEAT.md, memory)
- Semantic, keyword, and hybrid queries
- Retrieving full document content with `qmd get #docid`

**Commands:**
- `qmd search "keyword" -n 5` – fast keyword search
- `qmd vsearch "concept" -n 5` – semantic vector search
- `qmd query "natural language question" -n 5` – hybrid search with reranking
- `qmd get "#docid"` – retrieve document
- `qmd status` – check index state
- `qmd update` – re‑index changed files
- `qmd embed` – regenerate vectors after updates

**Permanent Rules:**
- Before asking "where is...", RUN QMD FIRST.
- When new files/folders added, run `qmd update && qmd embed`.
- Use `--json` when passing results to other tools.


### AgentMail 📧 (API-First Email Platform)
- **Connected:** 2026-04-27
- **API Key:** [AGENTMAIL_API_KEY]
- **Base URL:** https://api.agentmail.to/v0
- **Inbox ID:** openclawmainemail@agentmail.to
- **Display Name:** Openclaw Main Agent Mail
- **Status:** Active - emails sent/received successfully
- **Python SDK:** Installed in `/tmp/agentmail-venv/` (`pip install agentmail`)

**College Monitoring Targets (Subscription Requests Sent):**
- ✅ `news@stonybrook.edu` - SBU News Newsletter (Tuesday/Friday)
- ✅ `alumni@stonybrook.edu` - SB Matters alumni newsletter
- ✅ `admissions@ccny.cuny.edu` - City College undergraduate admissions
- ✅ `graduateadmissions@ccny.cuny.edu` - City College graduate admissions
- ❌ `cunynews@cuny.edu` - BLOCKED (bounces automated emails)

**Automation Stack:**
- **Python Virtual Environment:** `/tmp/agentmail-venv/bin/python`
- **Dependencies:** AgentMail SDK, httpx, pydantic, websockets
- **Script Location:** `~/.openclaw/workspace/skills/agentmail/scripts/`

**Security Notes:**
- ⚠️ **Webhook Security Required**: Incoming email = prompt injection vector
- **Solution**: Implement allowlist filter per AgentMail skill documentation
- **Isolate**: Review untrusted emails in separate session before acting
- **Credentials**: API key provides full access to inbox - protect accordingly

**Usage for Future Agents:**
1. Use API key from this TOOLS.md section
2. Import: `from agentmail import AgentMail`
3. Initialize: `client = AgentMail(api_key = "[REDACTED]")`
4. Send: `client.inboxes.messages.send(inbox_id="openclawmainemail@agentmail.to", ...)`
5. Monitor for college/scholarship emails in inbox

### Desktop Automation 🖥️ (PyAutoGUI)
- **Installed:** 2026-04-27
- **Virtual Environment:** `/tmp/desktop-automation/`
- **Dependencies:** `pyautogui`, `pillow`, `opencv-python`, `pygetwindow`
- **Purpose:** Web form automation for university newsletter subscriptions
- **Status:** ✅ Xvfb installed, headless browser automation ready
- **Display Solution:** ✅ Xvfb installed, using Selenium with headless Chrome

**University Web Forms (Require Browser Automation):**
- **Stony Brook News:** https://news.stonybrook.edu/subscribe-to-news/
- **Stony Brook Alumni:** https://sbmatters.stonybrook.edu/subscribe/
- **CCNY News:** https://www.ccny.cuny.edu/news (find subscribe form)
- **Forms Use:** Mailchimp, Contact Form 7, custom WordPress forms

**Next Automation Steps:**
1. ✅ **Xvfb installed**: Virtual display ready for headless automation
2. ✅ **Chrome & Selenium installed**: Headless browser automation configured
3. ✅ **Automation script created**: `scripts/university_form_automation.py`
4. **Map form field coordinates**: Requires manual inspection of university forms
5. **Implement form submission**: Fill with AgentMail email and submit
6. **Schedule periodic attempts**: Add to cron for regular form submission

### Webhook Security 🔒
- **Status**: Implemented (script ready), needs deployment
- **Script**: `scripts/agentmail_webhook.py`
- **Allowlist**: College domains and specific emails configured
- **Verification**: Signature validation with secret (optional)
- **Deployment**: Requires public URL with HTTPS (pending)
- **Alternative**: Use 6-hour inbox check for now

### College Monitoring Cron Jobs ⏰
- **Inbox Check**: Every 6 hours (`30 */6 * * *`)
- **Script**: `scripts/agentmail_check_cron.sh`
- **Logs**: `/root/.openclaw/workspace/logs/agentmail_check.log`
- **Memory Updates**: Auto-logs to daily memory files
- **Status**: ✅ Active and tested

### Scholarship Source Stack 🎓💸
- **Added:** 2026-05-12
- **Use for:** scholarship discovery, merit-aid research, NY/US grant checks, weekly scholarship sweeps, Mega academic/opportunity tasks, and daily brief scholarship slots.
- **Priority rule:** For Tony, default to NYC/NY first. Tony is currently a high-school junior with a strong / very good GPA and a tech/STEM/coding/software/engineering focus. Keep matching general until more profile details are known; verify deadline, eligibility, amount, application link, sponsor/original source, and whether an account/login is needed before recommending.
- **Daily brief opportunity rule:** Include both (1) best-fit scholarships and (2) NYC-area college/university programs, courses, internships, or pre-college opportunities that build coding/software/engineering skill and CV strength. For each scholarship, include a compact “how to get it” plan: requirements, materials needed, application path, and 1–3 next steps. Keep it high-signal and low-token.
- **Core sources:**
  - Fastweb — https://www.fastweb.com/
  - Naviance scholarship/college lookup — https://student.naviance.com/auth/fclookup
  - Sallie merit-based scholarships — https://www.sallie.com/scholarships/types/merit-based?utm_source=slmcom&utm_medium=web
  - NY HESC Excelsior Scholarship — https://hesc.ny.gov/find-aid/nys-grants-scholarships/excelsior-scholarship-program
  - Niche scholarships — https://www.niche.com/colleges/scholarships/
  - College Board BigFuture scholarships — https://bigfuture.collegeboard.org/pay-for-college/bigfuture-scholarships
  - Scholarships360 weird scholarships — https://scholarships360.org/scholarships/weird-scholarships/
  - CareerOneStop scholarship finder — https://www.careeronestop.org/Toolkit/Training/find-scholarships-detail.aspx?curPage=1&studyLevelfilter=Associate%20Degree&scholarshipId=9991168
- **Operational notes:**
  - Fastweb, Naviance, Niche, and BigFuture may require accounts or profile details; never create accounts, submit forms, or expose personal data without Tony's explicit approval.
  - HESC/Excelsior is NY-specific and should be checked for residency, income, credit-load, and post-graduation NY residency obligations.
  - CareerOneStop entries should be traced to the sponsor page before treating them as current.

### Self‑Improvement Activation 🧠
- **Status**: ✅ Active
- **Directory**: `workspace/.learnings/`
- **Files**: `LEARNINGS.md`, `ERRORS.md`, `FEATURE_REQUESTS.md`
- **Hook**: Internal self-improvement hook enabled in config
- **Usage**: Automatic logging of corrections and learnings

### Dozzle 🐳 (Docker Log Viewer)
- **Deployed:** 2026-05-06
- **Container:** `dozzle-lf0i-dozzle-1`
- **Image:** `amir20/dozzle:v9.0.1`
- **Port:** `0.0.0.0:32768->8080/tcp`
- **Access URL:** http://localhost:32768
- **Authentication:** Username: `admin`, Password: `securepassword123` (HTTP Basic Auth)
- **Purpose:** Real-time Docker container log viewing and monitoring
- **Features:**
  - Live log streaming
  - Container filtering
  - Log search
  - Multiple container support
  - Dark/light themes
  - HTTP Basic Authentication enabled

**Use this for:**
- Monitoring OpenClaw and other container logs
- Debugging container issues
- Real-time log observation
- Quick container status checks
- **Automation rule:** Daily maintenance should verify Dozzle is running/reachable as the Docker log viewer. For automated log analysis, prefer direct Docker logs and Telegraf metrics; use Dozzle as the UI/status check and manual follow-up surface.

### Uptime Kuma 📊 (Monitoring Tool)
- **Deployed:** 2026-05-06
- **Container:** `uptime-kuma-9ci2-uptime-kuma-1`
- **Image:** `louislam/uptime-kuma:2`
- **Port:** `0.0.0.0:65020->3001/tcp`
- **Access URL:** http://localhost:65020
- **Authentication:** Username: `admin`, Password: `admin123` (Form-based login)
- **Purpose:** Self-hosted monitoring service for uptime, response times, and service health
- **Features:**
  - HTTP(s)/TCP/Ping/DNS monitoring
  - Response time tracking
  - Notification integrations (Telegram, Discord, Email, etc.)
  - Customizable status pages
  - Historical data and analytics

**Use this for:**
- Monitoring OpenClaw service availability
- Tracking response times and performance
- Setting up alerts for service downtime
- Creating public status pages
- Monitoring external services (websites, APIs, etc.)
- **Automation rule:** Daily maintenance should use Uptime Kuma automatically as a health source. If the dashboard/API is reachable locally, check it; otherwise verify container health and recent errors for uptime-kuma-9ci2-uptime-kuma-1.

### Traefik Reverse Proxy
- **Container:** traefik-j74m-traefik-1
- **Status source:** Docker status/logs plus Telegraf/OpenClaw automation metrics.
- **Use this for:**
  - Reverse proxy/routing checks
  - Debugging route/domain/service exposure problems
  - Inspecting recent Traefik warnings/errors when services are unreachable
- **Automation rule:** Daily maintenance should verify the container is running and inspect recent logs for errors/warnings when checking VPS health. Use direct Docker logs/metrics in automated runs; only open dashboards or terminals when debugging needs it.

### Telegraf Host Metrics 📈
- **Installed:** 2026-05-18
- **Method:** Official InfluxData APT repository, package `telegraf` 1.38.4-1
- **Repo clone:** `/root/telegraf`
- **Config:** `/etc/telegraf/telegraf.conf`
- **Service:** `telegraf.service` enabled and running under the `telegraf` user
- **Live metrics:** `http://127.0.0.1:9273/metrics` via `outputs.prometheus_client`
- **Recent metric log:** `/var/log/telegraf/metrics.out` via `outputs.file`
- **Helper:** `openclaw-telegraf-metrics summary|automation|raw|recent [line_limit]`
- **Automation helper:** `openclaw-telegraf-metrics automation [line_limit]` shows native OpenClaw/VPS automation metrics.
- **Configured inputs:** `cpu`, `mem`, `swap`, `disk`, `diskio`, `net`, `processes`, `system`, `kernel` pressure stats, `internal`, `systemd_units`, `exec`, and `procstat` for Telegraf, the OpenClaw gateway, Codex app server, AgentMail webhook, cron, Docker, Uptime Kuma, Dozzle, and Traefik processes.
- **Automation metrics source:** `/usr/local/bin/openclaw-automation-metrics`, run by Telegraf through a narrow sudoers entry at `/etc/sudoers.d/telegraf-openclaw-metrics`, emits Influx line protocol for service status, key container status, cron inventory counts, and log freshness.
- **OpenClaw integration:** `HEARTBEAT.md` and the `daily-maintenance` OpenClaw cron now check `openclaw-telegraf-metrics summary` and `automation` before reporting VPS/system health. Daily maintenance also automatically checks Uptime Kuma container health, Traefik status/logs, and Dozzle reachability.
- **Auto-heal maintenance:** `scripts/daily-maintenance.sh` is now the safe auto-heal script. A host/root cron runs it at 03:30 America/New_York with `AUTO_UPDATE=1` so OpenClaw package updates can run outside the gateway process tree. The script performs a safety gate before updates, records pre-change snapshots under `memory/maintenance/prechange-*`, applies targeted fixes, retries after diagnostics, and verifies post-change OpenClaw health. The OpenClaw daily-maintenance cron runs at 04:00 America/New_York as the review/report/follow-up pass, using `AUTO_UPDATE=0` verification and applying one targeted safe fix/retry if the host pass failed. Risky fixes still report instead of blindly changing firewall/routes/auth/destructive data.
- **Docker note:** Docker input remains intentionally disabled because Docker socket access is effectively privileged. The old `openclaw-telegraf` Docker container was stopped and its restart policy disabled on 2026-05-18; host `telegraf.service` is now the monitoring source of truth.
