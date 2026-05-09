# 📋 SUBAGENT SETUP GUIDE

This document ensures all agents (main, volt, mega) and future subagents can access configured tools and skills seamlessly.

## 🏗️ CURRENT AGENT ARCHITECTURE

### Configured Agents:
1. **main** (Oboz) - Primary decision/routing agent
2. **volt** - Coding/technical executor
3. **mega** - School/research/thinking agent

### Shared Resources:
- **Workspace**: `/root/.openclaw/workspace` (all agents)
- **Configuration**: `~/.openclaw/openclaw.json` (agent definitions)
- **Skills Directory**: `workspace/skills/` (shared skills)
- **Memory Files**: `MEMORY.md`, `TOOLS.md`, `AGENTS.md`

## 🔧 AGENTMAIL INTEGRATION (CRITICAL)

### Configuration Status: ✅ ACTIVE
- **Email**: `openclawmainemail@agentmail.to`
- **API Key**: See `TOOLS.md` (AgentMail section)
- **Virtual Environment**: `/root/.openclaw/workspace/.venv-agentmail/`
- **Setup Script**: `scripts/agentmail-setup.sh`

### For Subagents to Use AgentMail:
```python
#!/usr/bin/env python3
import sys
sys.path.insert(0, '/root/.openclaw/workspace/.venv-agentmail/lib/python3.12/site-packages')
from agentmail import AgentMail
import re

# Get API key from TOOLS.md
with open('/root/.openclaw/workspace/TOOLS.md', 'r') as f:
    content = f.read()
    lines = content.split('\n')
    api_key = None
    for line in lines:
        if 'API Key:' in line:
            parts = line.split('API Key:')
            if len(parts) > 1:
                api_key = parts[1].strip().replace('**', '').strip()
                break

client = AgentMail(api_key=api_key)
# Use client...
```

### Quick Test Command:
```bash
/root/.openclaw/workspace/.venv-agentmail/bin/python -c "from agentmail import AgentMail; import re; import sys; exec(open('/root/.openclaw/workspace/scripts/agentmail-setup.sh').read())"
```

## 🎓 COLLEGE MONITORING PIPELINE

### Current Status:
- **Subscription Requests Sent**: `news@stonybrook.edu`, `alumni@stonybrook.edu`, `admissions@ccny.cuny.edu`, `graduateadmissions@ccny.cuny.edu`
- **Blocked**: `cunynews@cuny.edu` (bounces automated emails)
- **Next Actions**: Monitor inbox for confirmations, setup webhook security

### For Subagents Handling College Monitoring:
1. **Check AgentMail inbox** for subscription confirmations
2. **Monitor** for scholarship deadline emails
3. **Process** using webhook with security filters
4. **Update** `MEMORY.md` with new opportunities

## ⚙️ DESKTOP AUTOMATION SETUP

### Status: 🚧 PARTIALLY INSTALLED
- **Dependencies**: `pyautogui`, `pillow`, `opencv-python`, `pygetwindow`
- **Virtual Env**: `/tmp/desktop-automation/` (temporary)
- **Missing**: Xvfb (X virtual framebuffer for headless automation)
- **Purpose**: Web form automation for university newsletter subscriptions

### Installation for Subagents:
```bash
# If Xvfb needed:
apt-get install xvfb

# Python dependencies (already in temp venv):
python3 -m venv /root/.openclaw/workspace/.venv-desktop
/root/.openclaw/workspace/.venv-desktop/bin/pip install pyautogui pillow opencv-python pygetwindow
```

## 📅 CRON & HEARTBEAT INTEGRATION

### Current Cron Jobs:
```bash
*/30 * * * * /usr/bin/openclaw heartbeat
# GitHub monitoring (tony11-cpu repos)
# QMD updates via HEARTBEAT.md
```

### HEARTBEAT.md Commands:
- Morning brief (9 AM EST) - tech/AI/college updates
- QMD index update (6 AM EST)
- System health checks
- Zapier MCP email checks

### For Subagents Triggered by Cron:
1. **Check agent configuration** in `openclaw.json`
2. **Use appropriate bot tokens** for Telegram channels
3. **Access shared workspace** for files and memory
4. **Log actions** to `memory/YYYY-MM-DD.md`

## 🔐 SECURITY PROTOCOLS

### AgentMail Webhook Security (CRITICAL):
- **Risk**: Incoming emails = prompt injection vectors
- **Required**: Allowlist filter for trusted senders
- **Implementation**: See `skills/agentmail/SKILL.md` for webhook security guide
- **Action**: Implement before processing incoming emails

### Credential Management:
- **Location**: `TOOLS.md` (single source of truth)
- **Access**: All agents can read
- **Security**: No credentials in code or environment variables
- **Updates**: Update `TOOLS.md`, then notify all agents

## 🚀 STARTUP SEQUENCE FOR SUBAGENTS

### Recommended Startup Checklist:
```bash
#!/bin/bash
# subagent-startup.sh

# 1. Verify workspace access
ls /root/.openclaw/workspace/TOOLS.md || echo "Workspace not accessible"

# 2. Check AgentMail setup
/root/.openclaw/workspace/scripts/agentmail-setup.sh

# 3. Verify Python environments exist
test -d /root/.openclaw/workspace/.venv-agentmail || echo "Warning: AgentMail venv missing"

# 4. Check memory files
test -f /root/.openclaw/workspace/MEMORY.md || echo "Warning: MEMORY.md missing"

# 5. Verify skill access
test -d /root/.openclaw/workspace/skills/agentmail || echo "Warning: AgentMail skill missing"
```

### Agent-Specific Configuration:
- **main/oboz**: Decision routing, overall coordination
- **volt**: Technical execution, GitHub operations, automation
- **mega**: Research, school work, deep thinking, college monitoring

## 📁 FILE STRUCTURE REFERENCE

```
~/.openclaw/
├── openclaw.json          # Master configuration
├── workspace/             # Shared workspace
│   ├── TOOLS.md          # Credentials & configurations
│   ├── MEMORY.md         # Long-term memory
│   ├── AGENTS.md         # Agent roles/routing
│   ├── scripts/          # Automation scripts
│   └── skills/           # Installed skills
├── agents/               # Agent-specific data
│   ├── main/            # Oboz agent data
│   ├── volt/            # Volt agent data  
│   └── mega/            # Mega agent data
└── credentials/          # Secure credential storage
```

## 🛠️ TROUBLESHOOTING

### Common Issues & Solutions:

1. **AgentMail API Key Not Found**:
   ```bash
   grep -n "API Key" /root/.openclaw/workspace/TOOLS.md
   ```

2. **Python Import Errors**:
   ```bash
   # Use the shared virtual environment
   /root/.openclaw/workspace/.venv-agentmail/bin/python your_script.py
   ```

3. **Missing Dependencies**:
   ```bash
   # Install to shared venv
   /root/.openclaw/workspace/.venv-agentmail/bin/pip install missing-package
   ```

4. **Workspace Access Denied**:
   ```bash
   # Check permissions
   ls -la /root/.openclaw/workspace/
   ```

### Testing Subagent Readiness:
```bash
# Run comprehensive test
/root/.openclaw/workspace/scripts/agentmail-setup.sh && \
echo "✅ AgentMail ready" && \
test -f /root/.openclaw/workspace/TOOLS.md && \
echo "✅ TOOLS.md accessible" && \
test -f /root/.openclaw/workspace/MEMORY.md && \
echo "✅ MEMORY.md accessible" && \
echo "🎉 Subagent environment ready!"
```

## 📞 RESPONSIBILITY MATRIX

| Agent | Primary Responsibilities | Secondary |
|-------|--------------------------|-----------|
| **main/oboz** | Routing decisions, coordination, simple tasks | All |
| **volt** | Coding, technical work, GitHub, automation | System administration |
| **mega** | School/research, deep thinking, college monitoring | Analysis, explanations |

## 🔄 COORDINATION PROTOCOLS

1. **Memory Updates**: Always update `MEMORY.md` with significant actions
2. **Configuration Changes**: Update `TOOLS.md`, then notify other agents
3. **Error Handling**: Log errors to `memory/YYYY-MM-DD.md`
4. **Skill Installation**: Use `clawhub` and document in `TOOLS.md`

---

**LAST UPDATED**: 2026-04-27  
**BY**: Oboz (main agent)  
**STATUS**: ✅ AgentMail operational, 🚧 Desktop automation pending, 🔄 All agents configured