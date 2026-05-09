# HEARTBEAT.md – System Checklist

Check these items on each heartbeat; notify if action needed.

## Daily Checks (run at specific times)

### 9 AM Eastern – Morning Tech/AI/College Brief
- Check if script exists: ~/.openclaw/workspace/scripts/morning-brief.sh
- Run morning brief and log to memory

### 6 AM Eastern – QMD Index Update  
- Run: `qmd update`
- Run: `qmd embed`
- Confirm index is fresh

## Regular Checks (every heartbeat)

### Email & Communications
- [ ] Check AgentMail for college/scholarship emails
- [ ] Log any confirmations or new opportunities to memory
- [ ] Check for urgent messages in Telegram channels

### System Health
- [ ] OpenClaw gateway process running
- [ ] Disk usage (<85%)
- [ ] Memory available (>1GiB)
- [ ] Swap usage (<50%)
- [ ] Recent security audit no new critical findings

### Automation Status
- [ ] Cron jobs running (check last execution)
- [ ] AgentMail inbox check completed last 6h
- [ ] GitHub monitoring active
- [ ] Memory files being maintained

### Updates & Maintenance
- [ ] Check for OpenClaw updates
- [ ] Check for skill updates via ClawHub
- [ ] Review session transcripts for pruning
- [ ] Backup critical configs

## Actions
- If any check fails or needs attention, notify Tony
- Log completed checks to memory/YYYY-MM-DD.md
- Keep notifications minimal; only interrupt if urgent