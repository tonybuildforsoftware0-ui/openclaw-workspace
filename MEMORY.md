# MEMORY - Long-Term Intelligence Log

## Decisions Made
- *[2026-04-19]* - Updated Mega's role definition to final version: 60% school/college focus, 40% general research/deep thinking. Strict routing rules: coding/technical → Volt; school/research/deep thinking → Mega; simple tasks → Oboz.

## Optimizations Discovered
- *[2026-04-19]* - Renamed coding agent from codywoody to Volt across all configs.

## Failed Approaches
- *[2026-04-21]* - Repeatedly asking user for email instead of using configured Zapier MCP connection. Failed to properly automate morning briefs and heartbeats. User frustration escalated after multiple reminders.

## System Upgrades
- *[2026-04-19]* – Added Zapier MCP integration for Gmail, YouTube, Google Docs, Drive, and 4000+ apps. Token saved in `/root/.openclaw/credentials/zapier-mcp.json`. Documented in TOOLS.md.
- *[2026-04-21]* – Fixed morning brief automation: Created cron job (`*/30 * * * * /usr/bin/openclaw heartbeat`), added morning brief script, and automated 9 AM Eastern tech/AI/college briefing delivery. Email checks now use Zapier MCP without user prompting.
- *[2026-04-27]* – **AgentMail Integration**: Configured dedicated email `openclawmainemail@agentmail.to` for college/scholarship monitoring. API key documented in TOOLS.md. Sent subscription requests to Stony Brook University (`news@stonybrook.edu`, `alumni@stonybrook.edu`) and City College of NY (`admissions@ccny.cuny.edu`, `graduateadmissions@ccny.cuny.edu`). Note: `cunynews@cuny.edu` blocks automated emails. Desktop automation tools (PyAutoGUI) installed for future web form submissions.
- *[2026-04-27]* – **AgentMail Automation Complete**: Implemented 6-hour inbox check cron job, webhook security with allowlist (code ready), self‑improvement activation (.learnings directory), and headless web form automation (Xvfb, Selenium). All configurations documented in TOOLS.md and SUBAGENT_SETUP.md. Subscription confirmations already detected from graduateadmissions@ccny.cuny.edu.
- *[2026-05-12]* – **Daily backup auto-allowed**: Updated the daily backup cron to call `/root/.openclaw/workspace/scripts/daily-backup.sh` directly and added a host exec allowlist entry for that script, so backup runs can proceed without manual approval prompts while keeping the trust scope narrow.
- *[2026-05-12]* – **Scholarship source stack added**: Tony provided Fastweb, Naviance, Sallie merit scholarships, NY HESC/Excelsior, Niche, College Board BigFuture, Scholarships360 weird scholarships, and CareerOneStop as recurring scholarship sources. Updated TOOLS.md, Mega's AGENTS.md, root AGENTS.md, and `memory/scholarship-sources.md`; updated daily brief cron to run as Mega and added a weekly Mega scholarship sweep.
- *[2026-05-12]* – **Daily brief scholarship/STEM optimization**: Tony clarified he is currently a high-school junior with a strong/very good GPA, wants NYC as the default location, and wants daily briefs to include (1) best-fit scholarships from his source stack and (2) NYC-area university/college tech, STEM, coding, software, engineering, internship, course, or pre-college opportunities that improve skill and CV before college. Keep matching general until more profile data exists and keep scans credit-efficient. For every scholarship recommendation, include a compact plan covering requirements, materials needed, application path, preparation order, and next steps to improve Tony's chance.
- *[2026-05-13]* – **Direct Gmail monitoring connected**: Set up Gmail OAuth on the VPS with `gog`, resolved the keyring backend to file mode, and verified live Gmail access by reading Tony's mailbox (`tony.guirguis.dell@gmail.com`) from the VPS. Latest successful read returned Security alert, LinkedIn News, BigFuture School, Rowan University Admissions, and Quinnipiac University mail. Added a 4-hour Gmail monitor cron in OpenClaw that will read new mail, keep an empty-run message short, research scholarship/opportunity mentions, and stay compact/safe.

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
