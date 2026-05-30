# OpenClaw Installed Skills And Tools Audit - 2026-05-30

## OpenClaw Skills List
Skills (37/72 ready)
┌──────────┬─────────────────────────────────────┬────────────────────────────────────────────────┬────────────────────┐
│ Status   │ Skill                               │ Description                                    │ Source             │
├──────────┼─────────────────────────────────────┼────────────────────────────────────────────────┼────────────────────┤
│ ✓ ready  │ 🔐 1password                        │ Set up and use 1Password CLI (op). Use when    │ openclaw-workspace │
│          │                                     │ installing the CLI, enabling desktop app       │                    │
│          │                                     │ integration, signing in (single or multi-      │                    │
│          │                                     │ account), or reading/injecting/running         │                    │
│          │                                     │ secrets via op.                                │                    │
│ ✓ ready  │ 🌐 agent-browser                    │ Headless browser automation CLI optimized for  │ openclaw-workspace │
│          │                                     │ AI agents with accessibility tree snapshots    │                    │
│          │                                     │ and ref-based element selection                │                    │
│ ✓ ready  │ agentmail                           │ API-first email platform designed for AI       │ openclaw-workspace │
│          │                                     │ agents. Create and manage dedicated email      │                    │
│          │                                     │ inboxes, send and receive emails               │                    │
│          │                                     │ programmatically, and handle email-based       │                    │
│          │                                     │ workflows with webhooks and real-time events.  │                    │
│          │                                     │ Use when you need to set up agent email        │                    │
│          │                                     │ identity, send emails from agents, handle      │                    │
│          │                                     │ incoming email workflows, or replace           │                    │
│          │                                     │ traditional email providers like Gmail with    │                    │
│          │                                     │ agent-friendly infrastructure.                 │                    │
│ disabled │ 📝 apple-notes                      │ Create, view, edit, delete, search, move, or   │ openclaw-bundled   │
│          │                                     │ export Apple Notes via the memo CLI on macOS.  │                    │
│ disabled │ ⏰ apple-reminders                  │ List, add, edit, complete, or delete Apple     │ openclaw-bundled   │
│          │                                     │ Reminders and reminder lists via remindctl.    │                    │
│ disabled │ 🐻 bear-notes                       │ Create, search, and manage Bear notes via      │ openclaw-bundled   │
│          │                                     │ grizzly CLI.                                   │                    │
│ disabled │ 📰 blogwatcher                      │ Monitor blogs and RSS/Atom feeds for updates   │ openclaw-bundled   │
│          │                                     │ using the blogwatcher CLI.                     │                    │
│ disabled │ 🫐 blucli                           │ BluOS CLI (blu) for discovery, playback,       │ openclaw-bundled   │
│          │                                     │ grouping, and volume.                          │                    │
│ ✓ ready  │ browser-automation                  │ Use when controlling web pages with the        │ openclaw-extra     │
│          │                                     │ OpenClaw browser tool, especially multi-step   │                    │
│          │                                     │ flows, login checks, tab management, or        │                    │
│          │                                     │ recovery from stale refs/timeouts.             │                    │
│ disabled │ 📸 camsnap                          │ Capture frames or clips from RTSP/ONVIF        │ openclaw-bundled   │
│          │                                     │ cameras.                                       │                    │
│ ✓ ready  │ 🖼️ canvas                           │ Present HTML on connected OpenClaw node        │ openclaw-bundled   │
│          │                                     │ canvases, navigate/eval/snapshot, and debug    │                    │
│          │                                     │ canvas host URLs.                              │                    │
│ ✓ ready  │ clawhub                             │ Search, install, update, sync, or publish      │ openclaw-bundled   │
│          │                                     │ agent skills with the ClawHub CLI and          │                    │
│          │                                     │ registry.                                      │                    │
│ ✓ ready  │ 🧩 coding-agent                     │ Delegate coding work to Codex, Claude Code,    │ openclaw-bundled   │
│          │                                     │ OpenCode, or Pi as background workers; not     │                    │
│          │                                     │ simple edits or read-only code lookup.         │                    │
│ ✓ ready  │ desktop-control                     │ Advanced desktop automation with mouse,        │ openclaw-workspace │
│          │                                     │ keyboard, and screen control                   │                    │
│ ✓ ready  │ 🧭 diagram-maker                    │ Create SVG/HTML or Excalidraw diagrams for     │ openclaw-bundled   │
│          │                                     │ concepts, architecture, flows, and             │                    │
│          │                                     │ whiteboards.                                   │                    │
│ disabled │ 🎮 discord                          │ Discord message-tool ops: send/read/edit/      │ openclaw-bundled   │
│          │                                     │ delete, react, poll, pin, thread, search,      │                    │
│          │                                     │ presence, media/components.                    │                    │
│ disabled │ 🛌 eightctl                         │ Control Eight Sleep pods (status,              │ openclaw-bundled   │
│          │                                     │ temperature, alarms, schedules).               │                    │
│ disabled │ ✨ gemini                           │ Gemini CLI one-shot prompts, summaries,        │ openclaw-bundled   │
│          │                                     │ generation, skills, hooks, MCP, or Gemma       │                    │
│          │                                     │ routing.                                       │                    │
│ ✓ ready  │ gh-issues                           │ Fetch GitHub issues, select candidates, spawn  │ openclaw-bundled   │
│          │                                     │ background fix agents, open PRs, and           │                    │
│          │                                     │ optionally process PR review comments.         │                    │
│ disabled │ 🧲 gifgrep                          │ Search GIF providers with CLI/TUI, download    │ openclaw-bundled   │
│          │                                     │ results, and extract stills/sheets.            │                    │
│ ✓ ready  │ 🌳 git-essentials                   │ Essential Git commands and workflows for       │ openclaw-workspace │
│          │                                     │ version control, branching, and collaboration. │                    │
│ ✓ ready  │ 🐙 github                           │ Interact with GitHub using the `gh` CLI. Use   │ openclaw-workspace │
│          │                                     │ `gh issue`, `gh pr`, `gh run`, and `gh api`    │                    │
│          │                                     │ for issues, PRs, CI runs, and advanced         │                    │
│          │                                     │ queries.                                       │                    │
│ ✓ ready  │ 🎮 gog                              │ Google Workspace CLI for Gmail, Calendar,      │ openclaw-workspace │
│          │                                     │ Drive, Contacts, Sheets, and Docs.             │                    │
│ disabled │ 📍 goplaces                         │ Query Google Places for text search, place     │ openclaw-bundled   │
│          │                                     │ details, resolve, reviews, or scriptable JSON  │                    │
│          │                                     │ via goplaces.                                  │                    │
│ ✓ ready  │ healthcheck                         │ Audit/harden OpenClaw hosts: SSH, firewall,    │ openclaw-bundled   │
│          │                                     │ updates, exposure, backups, disk encryption,   │                    │
│          │                                     │ gateway security.                              │                    │
│ disabled │ 📧 himalaya                         │ Himalaya CLI for IMAP/SMTP mail: list, read,   │ openclaw-bundled   │
│          │                                     │ search, compose, reply, forward, copy, move,   │                    │
│          │                                     │ delete.                                        │                    │
│ disabled │ 📨 imsg                             │ iMessage/SMS CLI for listing chats, history,   │ openclaw-bundled   │
│          │                                     │ and sending messages via Messages.app.         │                    │
│ ✓ ready  │ 📰 last30days                       │ Research what people actually say about any    │ openclaw-workspace │
│          │                                     │ topic in the last 30 days. Pulls posts and     │                    │
│          │                                     │ engagement from Reddit, X, YouTube, TikTok,    │                    │
│          │                                     │ Hacker News, Polymarket, GitHub, and the web.  │                    │
│ ✓ ready  │ 📦 mcporter                         │ List, configure, authenticate, call, and       │ openclaw-bundled   │
│          │                                     │ inspect MCP servers/tools with mcporter over   │                    │
│          │                                     │ HTTP or stdio.                                 │                    │
│ ✓ ready  │ 🖼️ meme-maker                       │ Search meme templates, suggest formats, and    │ openclaw-bundled   │
│          │                                     │ generate local or hosted image memes.          │                    │
│ disabled │ 📊 model-usage                      │ Summarize CodexBar local cost logs by model    │ openclaw-bundled   │
│          │                                     │ for Codex or Claude, including current or      │                    │
│          │                                     │ full breakdowns.                               │                    │
│ ✓ ready  │ multi-search-engine                 │ Multi search engine integration with 17        │ openclaw-workspace │
│          │                                     │ engines (8 CN + 9 Global). Supports advanced   │                    │
│          │                                     │ search operators, time filters, site search,   │                    │
│          │                                     │ privacy engines, and WolframAlpha knowledge    │                    │
│          │                                     │ queries. No API keys required.                 │                    │
│ disabled │ 📄 nano-pdf                         │ Edit PDFs with natural-language instructions   │ openclaw-workspace │
│          │                                     │ using the nano-pdf CLI.                        │                    │
│ ✓ ready  │ node-connect                        │ Diagnose OpenClaw Android, iOS, or macOS node  │ openclaw-bundled   │
│          │                                     │ pairing, QR/setup code, route, auth, and       │                    │
│          │                                     │ connection failures.                           │                    │
│ ✓ ready  │ 🪲 node-inspect-debugger            │ Debug Node.js with node inspect, --inspect,    │ openclaw-bundled   │
│          │                                     │ breakpoints, CDP, heap, and CPU profiles.      │                    │
│ disabled │ 📝 notion                           │ Notion CLI/API for pages, Markdown content,    │ openclaw-bundled   │
│          │                                     │ data sources, files, comments, search,         │                    │
│          │                                     │ Workers, and raw API calls.                    │                    │
│ disabled │ 💎 obsidian                         │ Work with Obsidian vaults using the official   │ openclaw-bundled   │
│          │                                     │ obsidian CLI: read/search/create/edit notes,   │                    │
│          │                                     │ tasks, links, properties, plugins.             │                    │
│ ✓ ready  │ ontology                            │ Typed knowledge graph for structured agent     │ openclaw-workspace │
│          │                                     │ memory and composable skills. Use when         │                    │
│          │                                     │ creating/querying entities (Person, Project,   │                    │
│          │                                     │ Task, Event, Document), linking related        │                    │
│          │                                     │ objects, enforcing constraints, planning       │                    │
│          │                                     │ multi-step actions as graph transformations,   │                    │
│          │                                     │ or when skills need to share state. Trigger    │                    │
│          │                                     │ on "remember", "what do I know about", "link   │                    │
│          │                                     │ X to Y", "show dependencies", entity CRUD, or  │                    │
│          │                                     │ cross-skill data access.                       │                    │
│ disabled │ 🎤 openai-whisper                   │ Local speech-to-text with the Whisper CLI (no  │ openclaw-bundled   │
│          │                                     │ API key).                                      │                    │
│ disabled │ 🌐 openai-whisper-api               │ OpenAI Audio Transcriptions API via curl; gpt- │ openclaw-bundled   │
│          │                                     │ 4o-transcribe, mini, diarize, or whisper-1.    │                    │
│ disabled │ 💡 openhue                          │ Control Philips Hue lights and scenes via the  │ openclaw-bundled   │
│          │                                     │ OpenHue CLI.                                   │                    │
│ ✓ ready  │ 🧿 oracle                           │ Oracle CLI second-model review/debug/refactor/ │ openclaw-bundled   │
│          │                                     │ design with selected files, dry-run token      │                    │
│          │                                     │ checks, API or browser engine.                 │                    │
│ disabled │ 🛵 ordercli                         │ Foodora-only CLI for checking past orders and  │ openclaw-bundled   │
│          │                                     │ active order status (Deliveroo WIP).           │                    │
│ disabled │ 👀 peekaboo                         │ Capture and automate macOS UI with the         │ openclaw-bundled   │
│          │                                     │ Peekaboo CLI.                                  │                    │
│ ✓ ready  │ 📊 polymarket-trade                 │ Query Polymarket prediction markets. Check     │ openclaw-workspace │
│          │                                     │ odds, find trending markets, search events,    │                    │
│          │                                     │ track price movements.                         │                    │
│ ✓ ready  │ python-debugpy                      │ Debug Python with pdb, breakpoint(), post-     │ openclaw-bundled   │
│          │                                     │ mortem inspection, and debugpy remote attach.  │                    │
│ ✓ ready  │ 📝 qmd                              │ Local search/indexing CLI (BM25 + vectors +    │ openclaw-workspace │
│          │                                     │ rerank) with MCP mode.                         │                    │
│ disabled │ 🔊 sag                              │ ElevenLabs text-to-speech with mac-style say   │ openclaw-bundled   │
│          │                                     │ UX.                                            │                    │
│ ✓ ready  │ self-improvement                    │ Captures learnings, errors, and corrections    │ openclaw-workspace │
│          │                                     │ to enable continuous improvement. Use when:    │                    │
│          │                                     │ (1) A command or operation fails               │                    │
│          │                                     │ unexpectedly, (2) User corrects Claude ('No,   │                    │
│          │                                     │ that's wrong...', 'Actually...'), (3) User     │                    │
│          │                                     │ requests a capability that doesn't exist, (4)  │                    │
│          │                                     │ An external API or tool fails, (5) Claude      │                    │
│          │                                     │ realizes its knowledge is outdated or          │                    │
│          │                                     │ incorrect, (6) A better approach is            │                    │
│          │                                     │ discovered for a recurring task. Also review   │                    │
│          │                                     │ learnings before major tasks.                  │                    │
│ ✓ ready  │ 🧠 Self-Improving + Proactive Agent │ Self-reflection + Self-criticism + Self-       │ openclaw-workspace │
│          │                                     │ learning + Self-organizing memory. Agent       │                    │
│          │                                     │ evaluates its own work, catches mistakes, and  │                    │
│          │                                     │ improves permanently. Use when (1) a command,  │                    │
│          │                                     │ tool, API, or operation fails; (2) the user    │                    │
│          │                                     │ corrects you or rejects your work; (3) you     │                    │
│          │                                     │ realize your knowledge is outdated or          │                    │
│          │                                     │ incorrect; (4) you discover a better           │                    │
│          │                                     │ approach; (5) the user explicitly installs or  │                    │
│          │                                     │ references the skill for the current task.     │                    │
│ disabled │ 📜 session-logs                     │ Search and analyze your own session logs       │ openclaw-workspace │
│          │                                     │ (older/parent conversations) using jq.         │                    │
│ disabled │ 🔉 sherpa-onnx-tts                  │ Local text-to-speech via sherpa-onnx           │ openclaw-bundled   │
│          │                                     │ (offline, no cloud)                            │                    │
│ ✓ ready  │ skill-creator                       │ Create, edit, audit, tidy, validate, or        │ openclaw-bundled   │
│          │                                     │ restructure AgentSkills and SKILL.md files.    │                    │
│ ✓ ready  │ skill-vetter                        │ Security-first skill vetting for AI agents.    │ openclaw-workspace │
│          │                                     │ Use before installing any skill from           │                    │
│          │                                     │ ClawdHub, GitHub, or other sources. Checks     │                    │
│          │                                     │ for red flags, permission scope, and           │                    │
│          │                                     │ suspicious patterns.                           │                    │
│ disabled │ 💬 slack                            │ Slack tool actions: send/read/edit/delete      │ openclaw-bundled   │
│          │                                     │ messages, react, pin/unpin, list pins/         │                    │
│          │                                     │ reactions/emoji, member info.                  │                    │
│ disabled │ 🌊 songsee                          │ Generate spectrograms and feature-panel        │ openclaw-bundled   │
│          │                                     │ visualizations from audio with the songsee     │                    │
│          │                                     │ CLI.                                           │                    │
│ disabled │ 🔊 sonoscli                         │ Control Sonos speakers (discover/status/play/  │ openclaw-bundled   │
│          │                                     │ volume/group).                                 │                    │
│ ✓ ready  │ 🧪 spike                            │ Run throwaway prototypes to validate           │ openclaw-bundled   │
│          │                                     │ feasibility, compare approaches, and report a  │                    │
│          │                                     │ verdict.                                       │                    │
│ disabled │ 🎵 spotify-player                   │ Terminal Spotify playback/search via spogo     │ openclaw-bundled   │
│          │                                     │ (preferred) or spotify_player.                 │                    │
│ ✓ ready  │ subagent-ops                        │ Routing and delegation rules for oboz to       │ openclaw-workspace │
│          │                                     │ coordinate with Volt (coding) and Mega         │                    │
│          │                                     │ (school/research).                             │                    │
│ ✓ ready  │ 🧾 summarize                        │ Summarize URLs or files with the summarize     │ openclaw-workspace │
│          │                                     │ CLI (web, PDFs, images, audio, YouTube).       │                    │
│ ✓ ready  │ 🪝 taskflow                         │ Coordinate multi-step detached tasks as one    │ openclaw-bundled   │
│          │                                     │ durable TaskFlow job with owner context,       │                    │
│          │                                     │ state, waits, and child tasks.                 │                    │
│ ✓ ready  │ 📥 taskflow-inbox-triage            │ Example TaskFlow pattern for inbox triage,     │ openclaw-bundled   │
│          │                                     │ intent routing, waiting on replies, and later  │                    │
│          │                                     │ summaries.                                     │                    │
│ ✓ ready  │ 🔍 tavily                           │ Tavily web search, content extraction, and     │ openclaw-extra     │
│          │                                     │ research tools.                                │                    │
│ disabled │ ✅ things-mac                       │ Add, update, list, search, or inspect Things   │ openclaw-bundled   │
│          │                                     │ 3 todos, inbox, today, projects, areas, and    │                    │
│          │                                     │ tags on macOS.                                 │                    │
│ ✓ ready  │ 🧵 tmux                             │ Control tmux sessions/panes for interactive    │ openclaw-bundled   │
│          │                                     │ CLIs: list, capture output, send keys, paste   │                    │
│          │                                     │ text, monitor prompts.                         │                    │
│ disabled │ 📋 trello                           │ Manage Trello boards, lists, and cards via     │ openclaw-bundled   │
│          │                                     │ the Trello REST API.                           │                    │
│ disabled │ 🎬 video-frames                     │ Extract frames or short clips from videos      │ openclaw-bundled   │
│          │                                     │ using ffmpeg.                                  │                    │
│ disabled │ 📞 voice-call                       │ Start voice calls via the OpenClaw voice-call  │ openclaw-bundled   │
│          │                                     │ plugin.                                        │                    │
│ disabled │ 📱 wacli                            │ Send third-party WhatsApp messages or sync/    │ openclaw-bundled   │
│          │                                     │ search WhatsApp history via wacli, not normal  │                    │
│          │                                     │ active chats.                                  │                    │
│ ✓ ready  │ 🌤️ weather                          │ Get current weather and forecasts (no API key  │ openclaw-workspace │
│          │                                     │ required).                                     │                    │
│ disabled │ 🐦 xurl                             │ xurl CLI for authenticated X posts, replies,   │ openclaw-bundled   │
│          │                                     │ reads/search, DMs, media upload, followers,    │                    │
│          │                                     │ auth status, or raw v2 API calls.              │                    │
└──────────┴─────────────────────────────────────┴────────────────────────────────────────────────┴────────────────────┘

Tip: use `openclaw skills search`, `openclaw skills install`, and `openclaw skills update` for ClawHub-backed skills.

## OpenClaw Skills Check
Skills Status Check
Agent: main

Total: 72
✓ Eligible: 37
✓ Visible to model: 37
✓ Available as command: 36
Disabled: 35
Blocked by allowlist: 0
Excluded by agent allowlist: 0
✗ Missing requirements: 0

What this means:
  Eligible: installed and requirements pass; the agent may still exclude it.
  Visible to model: the agent can see the skill instructions during normal chat.
  Available as command: people, scripts, or cron jobs can call the skill explicitly.

Ready and visible to model:
  🔐 1password
  🌐 agent-browser
  agentmail
  browser-automation
  🖼️ canvas
  clawhub
  🧩 coding-agent
  desktop-control
  🧭 diagram-maker
  gh-issues
  🌳 git-essentials
  🐙 github
  🎮 gog
  healthcheck
  📰 last30days
  📦 mcporter
  🖼️ meme-maker
  multi-search-engine
  node-connect
  🪲 node-inspect-debugger
  ontology
  🧿 oracle
  📊 polymarket-trade
  python-debugpy
  📝 qmd
  self-improvement
  🧠 Self-Improving + Proactive Agent
  skill-creator
  skill-vetter
  🧪 spike
  subagent-ops
  🧾 summarize
  🪝 taskflow
  📥 taskflow-inbox-triage
  🔍 tavily
  🧵 tmux
  🌤️ weather

Tip: use `openclaw skills search`, `openclaw skills install`, and `openclaw skills update` for ClawHub-backed skills.

## Workspace Skill Directories
/root/.openclaw/workspace/skills/1password/SKILL.md
/root/.openclaw/workspace/skills/20206-02-10-clawhub-summarize-1-0-0/SKILL.md
/root/.openclaw/workspace/skills/agent-browser-clawdbot/SKILL.md
/root/.openclaw/workspace/skills/agentmail/SKILL.md
/root/.openclaw/workspace/skills/desktop-control/SKILL.md
/root/.openclaw/workspace/skills/git-essentials/SKILL.md
/root/.openclaw/workspace/skills/github/SKILL.md
/root/.openclaw/workspace/skills/gog/SKILL.md
/root/.openclaw/workspace/skills/last30days/SKILL.md
/root/.openclaw/workspace/skills/nano-pdf/SKILL.md
/root/.openclaw/workspace/skills/ontology/SKILL.md
/root/.openclaw/workspace/skills/openclaw-multi-search-engine/SKILL.md
/root/.openclaw/workspace/skills/polymarket-trade/SKILL.md
/root/.openclaw/workspace/skills/qmd/SKILL.md
/root/.openclaw/workspace/skills/self-improving-agent/SKILL.md
/root/.openclaw/workspace/skills/self-improving/SKILL.md
/root/.openclaw/workspace/skills/session-logs/SKILL.md
/root/.openclaw/workspace/skills/skill-vetter/SKILL.md
/root/.openclaw/workspace/skills/subagent-ops/SKILL.md
/root/.openclaw/workspace/skills/summarize/SKILL.md
/root/.openclaw/workspace/skills/weather/SKILL.md

## Bundled Skill Directories
/usr/lib/node_modules/openclaw/skills/1password/SKILL.md
/usr/lib/node_modules/openclaw/skills/apple-notes/SKILL.md
/usr/lib/node_modules/openclaw/skills/apple-reminders/SKILL.md
/usr/lib/node_modules/openclaw/skills/bear-notes/SKILL.md
/usr/lib/node_modules/openclaw/skills/blogwatcher/SKILL.md
/usr/lib/node_modules/openclaw/skills/blucli/SKILL.md
/usr/lib/node_modules/openclaw/skills/camsnap/SKILL.md
/usr/lib/node_modules/openclaw/skills/canvas/SKILL.md
/usr/lib/node_modules/openclaw/skills/clawhub/SKILL.md
/usr/lib/node_modules/openclaw/skills/coding-agent/SKILL.md
/usr/lib/node_modules/openclaw/skills/diagram-maker/SKILL.md
/usr/lib/node_modules/openclaw/skills/discord/SKILL.md
/usr/lib/node_modules/openclaw/skills/eightctl/SKILL.md
/usr/lib/node_modules/openclaw/skills/gemini/SKILL.md
/usr/lib/node_modules/openclaw/skills/gh-issues/SKILL.md
/usr/lib/node_modules/openclaw/skills/gifgrep/SKILL.md
/usr/lib/node_modules/openclaw/skills/github/SKILL.md
/usr/lib/node_modules/openclaw/skills/gog/SKILL.md
/usr/lib/node_modules/openclaw/skills/goplaces/SKILL.md
/usr/lib/node_modules/openclaw/skills/healthcheck/SKILL.md
/usr/lib/node_modules/openclaw/skills/himalaya/SKILL.md
/usr/lib/node_modules/openclaw/skills/imsg/SKILL.md
/usr/lib/node_modules/openclaw/skills/mcporter/SKILL.md
/usr/lib/node_modules/openclaw/skills/meme-maker/SKILL.md
/usr/lib/node_modules/openclaw/skills/model-usage/SKILL.md
/usr/lib/node_modules/openclaw/skills/nano-pdf/SKILL.md
/usr/lib/node_modules/openclaw/skills/node-connect/SKILL.md
/usr/lib/node_modules/openclaw/skills/node-inspect-debugger/SKILL.md
/usr/lib/node_modules/openclaw/skills/notion/SKILL.md
/usr/lib/node_modules/openclaw/skills/obsidian/SKILL.md
/usr/lib/node_modules/openclaw/skills/openai-whisper-api/SKILL.md
/usr/lib/node_modules/openclaw/skills/openai-whisper/SKILL.md
/usr/lib/node_modules/openclaw/skills/openhue/SKILL.md
/usr/lib/node_modules/openclaw/skills/oracle/SKILL.md
/usr/lib/node_modules/openclaw/skills/ordercli/SKILL.md
/usr/lib/node_modules/openclaw/skills/peekaboo/SKILL.md
/usr/lib/node_modules/openclaw/skills/python-debugpy/SKILL.md
/usr/lib/node_modules/openclaw/skills/sag/SKILL.md
/usr/lib/node_modules/openclaw/skills/session-logs/SKILL.md
/usr/lib/node_modules/openclaw/skills/sherpa-onnx-tts/SKILL.md
/usr/lib/node_modules/openclaw/skills/skill-creator/SKILL.md
/usr/lib/node_modules/openclaw/skills/slack/SKILL.md
/usr/lib/node_modules/openclaw/skills/songsee/SKILL.md
/usr/lib/node_modules/openclaw/skills/sonoscli/SKILL.md
/usr/lib/node_modules/openclaw/skills/spike/SKILL.md
/usr/lib/node_modules/openclaw/skills/spotify-player/SKILL.md
/usr/lib/node_modules/openclaw/skills/summarize/SKILL.md
/usr/lib/node_modules/openclaw/skills/taskflow-inbox-triage/SKILL.md
/usr/lib/node_modules/openclaw/skills/taskflow/SKILL.md
/usr/lib/node_modules/openclaw/skills/things-mac/SKILL.md
/usr/lib/node_modules/openclaw/skills/tmux/SKILL.md
/usr/lib/node_modules/openclaw/skills/trello/SKILL.md
/usr/lib/node_modules/openclaw/skills/video-frames/SKILL.md
/usr/lib/node_modules/openclaw/skills/voice-call/SKILL.md
/usr/lib/node_modules/openclaw/skills/wacli/SKILL.md
/usr/lib/node_modules/openclaw/skills/weather/SKILL.md
/usr/lib/node_modules/openclaw/skills/xurl/SKILL.md

## Plugin Skill Directories

## OpenClaw Plugins List
Plugins (7/92 enabled)
Source roots:
  stock: /usr/lib/node_modules/openclaw/dist/extensions

┌──────────────┬──────────┬──────────┬──────────┬──────────────────────────────────────────────────────────┬───────────┐
│ Name         │ ID       │ Format   │ Status   │ Source                                                   │ Version   │
├──────────────┼──────────┼──────────┼──────────┼──────────────────────────────────────────────────────────┼───────────┤
│ Active       │ active-  │ openclaw │ disabled │ stock:active-memory/index.js                             │           │
│ Memory       │ memory   │          │          │ Runs a bounded blocking memory sub-agent before          │           │
│              │          │          │          │ eligible conversational replies and injects relevant     │           │
│              │          │          │          │ memory into prompt context.                              │           │
│ @openclaw/   │ admin-   │ openclaw │ disabled │ stock:admin-http-rpc/index.js                            │ 2026.5.27 │
│ admin-http-  │ http-rpc │          │          │                                                          │           │
│ rpc          │          │          │          │                                                          │           │
│ @openclaw/   │ alibaba  │ openclaw │ disabled │ stock:alibaba/index.js                                   │ 2026.5.27 │
│ alibaba-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ anthropi │ openclaw │ disabled │ stock:anthropic/index.js                                 │ 2026.5.27 │
│ anthropic-   │ c        │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ arcee    │ openclaw │ disabled │ stock:arcee/index.js                                     │ 2026.5.27 │
│ arcee-       │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Azure Speech │ azure-   │ openclaw │ disabled │ stock:azure-speech/index.js                              │ 2026.5.27 │
│              │ speech   │          │          │ Azure AI Speech text-to-speech (MP3, native Ogg/Opus     │           │
│              │          │          │          │ voice notes, PCM telephony).                             │           │
│ Bonjour      │ bonjour  │ openclaw │ disabled │ stock:bonjour/index.js                                   │ 2026.5.27 │
│ Gateway      │          │          │          │ Advertise the local OpenClaw gateway over Bonjour/mDNS.  │           │
│ Discovery    │          │          │          │                                                          │           │
│ @openclaw/   │ browser  │ openclaw │ enabled  │ stock:browser/index.js                                   │ 2026.5.27 │
│ browser-     │          │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ byteplus │ openclaw │ disabled │ stock:byteplus/index.js                                  │ 2026.5.27 │
│ byteplus-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Canvas       │ canvas   │ openclaw │ disabled │ stock:canvas/index.js                                    │ 2026.5.27 │
│              │          │          │          │ Experimental Canvas control and A2UI rendering surfaces  │           │
│              │          │          │          │ for paired nodes.                                        │           │
│ @openclaw/   │ cerebras │ openclaw │ disabled │ stock:cerebras/index.js                                  │ 2026.5.27 │
│ cerebras-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ chutes   │ openclaw │ disabled │ stock:chutes/index.js                                    │ 2026.5.27 │
│ chutes-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ clickcla │ openclaw │ disabled │ stock:clickclack/index.js                                │ 2026.5.27 │
│ clickclack   │ ck       │          │          │                                                          │           │
│ @openclaw/   │ cloudfla │ openclaw │ disabled │ stock:cloudflare-ai-gateway/index.js                     │ 2026.5.27 │
│ cloudflare-  │ re-ai-   │          │          │                                                          │           │
│ ai-gateway-  │ gateway  │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ comfy    │ openclaw │ disabled │ stock:comfy/index.js                                     │ 2026.5.27 │
│ comfy-       │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ copilot- │ openclaw │ disabled │ stock:copilot-proxy/index.js                             │ 2026.5.27 │
│ copilot-     │ proxy    │          │          │                                                          │           │
│ proxy        │          │          │          │                                                          │           │
│ @openclaw/   │ deepgram │ openclaw │ disabled │ stock:deepgram/index.js                                  │ 2026.5.27 │
│ deepgram-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ deepinfr │ openclaw │ disabled │ stock:deepinfra/index.js                                 │ 2026.5.27 │
│ deepinfra-   │ a        │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ deepseek │ openclaw │ disabled │ stock:deepseek/index.js                                  │ 2026.5.27 │
│ deepseek-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Device       │ device-  │ openclaw │ disabled │ stock:device-pair/index.js                               │           │
│ Pairing      │ pair     │          │          │ Generate setup codes and approve device pairing          │           │
│              │          │          │          │ requests.                                                │           │
│ Document     │ document │ openclaw │ disabled │ stock:document-extract/index.js                          │ 2026.5.27 │
│ Extraction   │ -extract │          │          │ Extract text and fallback page images from local         │           │
│              │          │          │          │ document attachments.                                    │           │
│ @openclaw/   │ duckduck │ openclaw │ disabled │ stock:duckduckgo/index.js                                │ 2026.5.27 │
│ duckduckgo-  │ go       │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ elevenla │ openclaw │ disabled │ stock:elevenlabs/index.js                                │ 2026.5.27 │
│ elevenlabs-  │ bs       │          │          │                                                          │           │
│ speech       │          │          │          │                                                          │           │
│ @openclaw/   │ exa      │ openclaw │ disabled │ stock:exa/index.js                                       │ 2026.5.27 │
│ exa-plugin   │          │          │          │                                                          │           │
│ @openclaw/   │ fal      │ openclaw │ disabled │ stock:fal/index.js                                       │ 2026.5.27 │
│ fal-provider │          │          │          │                                                          │           │
│ File         │ file-    │ openclaw │ disabled │ stock:file-transfer/index.js                             │ 2026.5.27 │
│ Transfer     │ transfer │          │          │ Fetch, list, and write files on paired nodes via         │           │
│              │          │          │          │ dedicated node commands. Bypasses bash stdout            │           │
│              │          │          │          │ truncation by using base64 over node.invoke for          │           │
│              │          │          │          │ binaries up to 16 MB.                                    │           │
│ @openclaw/   │ firecraw │ openclaw │ disabled │ stock:firecrawl/index.js                                 │ 2026.5.27 │
│ firecrawl-   │ l        │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ firework │ openclaw │ disabled │ stock:fireworks/index.js                                 │ 2026.5.27 │
│ fireworks-   │ s        │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ github-  │ openclaw │ disabled │ stock:github-copilot/index.js                            │ 2026.5.27 │
│ github-      │ copilot  │          │          │                                                          │           │
│ copilot-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ google   │ openclaw │ disabled │ stock:google/index.js                                    │ 2026.5.27 │
│ google-      │          │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ gradium  │ openclaw │ disabled │ stock:gradium/index.js                                   │ 2026.5.27 │
│ gradium-     │          │          │          │                                                          │           │
│ speech       │          │          │          │                                                          │           │
│ @openclaw/   │ groq     │ openclaw │ disabled │ stock:groq/index.js                                      │ 2026.5.27 │
│ groq-        │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ huggingf │ openclaw │ disabled │ stock:huggingface/index.js                               │ 2026.5.27 │
│ huggingface- │ ace      │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ imessage │ openclaw │ disabled │ stock:imessage/index.js                                  │ 2026.5.27 │
│ imessage     │          │          │          │                                                          │           │
│ Inworld      │ inworld  │ openclaw │ disabled │ stock:inworld/index.js                                   │ 2026.5.27 │
│              │          │          │          │ Inworld streaming text-to-speech (MP3, OGG_OPUS, PCM     │           │
│              │          │          │          │ telephony).                                              │           │
│ @openclaw/   │ irc      │ openclaw │ disabled │ stock:irc/index.js                                       │ 2026.5.27 │
│ irc          │          │          │          │                                                          │           │
│ @openclaw/   │ kilocode │ openclaw │ disabled │ stock:kilocode/index.js                                  │ 2026.5.27 │
│ kilocode-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ kimi     │ openclaw │ disabled │ stock:kimi-coding/index.js                               │ 2026.5.27 │
│ kimi-        │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ litellm  │ openclaw │ disabled │ stock:litellm/index.js                                   │ 2026.5.27 │
│ litellm-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ LLM Task     │ llm-task │ openclaw │ disabled │ stock:llm-task/index.js                                  │ 2026.5.27 │
│              │          │          │          │ Generic JSON-only LLM tool for structured tasks          │           │
│              │          │          │          │ callable from workflows.                                 │           │
│ @openclaw/   │ lmstudio │ openclaw │ disabled │ stock:lmstudio/index.js                                  │ 2026.5.27 │
│ lmstudio-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ mattermo │ openclaw │ disabled │ stock:mattermost/index.js                                │ 2026.5.27 │
│ mattermost   │ st       │          │          │                                                          │           │
│ @openclaw/   │ memory-  │ openclaw │ enabled  │ stock:memory-core/index.js                               │ 2026.5.27 │
│ memory-core  │ core     │          │          │                                                          │           │
│ Memory Wiki  │ memory-  │ openclaw │ disabled │ stock:memory-wiki/index.js                               │ 2026.5.27 │
│              │ wiki     │          │          │ Persistent wiki compiler and Obsidian-friendly           │           │
│              │          │          │          │ knowledge vault for OpenClaw.                            │           │
│ @openclaw/   │ microsof │ openclaw │ disabled │ stock:microsoft/index.js                                 │ 2026.5.27 │
│ microsoft-   │ t        │          │          │                                                          │           │
│ speech       │          │          │          │                                                          │           │
│ @openclaw/   │ microsof │ openclaw │ disabled │ stock:microsoft-foundry/index.js                         │ 2026.5.27 │
│ microsoft-   │ t-       │          │          │                                                          │           │
│ foundry      │ foundry  │          │          │                                                          │           │
│ Claude       │ migrate- │ openclaw │ disabled │ stock:migrate-claude/index.js                            │ 2026.5.27 │
│ Migration    │ claude   │          │          │ Imports Claude Code and Claude Desktop instructions,     │           │
│              │          │          │          │ MCP servers, skills, and safe configuration into         │           │
│              │          │          │          │ OpenClaw.                                                │           │
│ Hermes       │ migrate- │ openclaw │ disabled │ stock:migrate-hermes/index.js                            │ 2026.5.27 │
│ Migration    │ hermes   │          │          │ Imports Hermes configuration, memories, skills, and      │           │
│              │          │          │          │ supported credentials into OpenClaw.                     │           │
│ @openclaw/   │ minimax  │ openclaw │ disabled │ stock:minimax/index.js                                   │ 2026.5.27 │
│ minimax-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ mistral  │ openclaw │ disabled │ stock:mistral/index.js                                   │ 2026.5.27 │
│ mistral-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ moonshot │ openclaw │ disabled │ stock:moonshot/index.js                                  │ 2026.5.27 │
│ moonshot-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ nvidia   │ openclaw │ disabled │ stock:nvidia/index.js                                    │ 2026.5.27 │
│ nvidia-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ OC Path      │ oc-path  │ openclaw │ disabled │ stock:oc-path/index.js                                   │ 2026.5.27 │
│              │          │          │          │ Adds the openclaw path CLI for oc:// workspace file      │           │
│              │          │          │          │ addressing.                                              │           │
│ @openclaw/   │ ollama   │ openclaw │ disabled │ stock:ollama/index.js                                    │ 2026.5.27 │
│ ollama-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ OpenProse    │ open-    │ openclaw │ disabled │ stock:open-prose/index.js                                │ 2026.5.27 │
│              │ prose    │          │          │ OpenProse VM skill pack with a /prose slash command.     │           │
│ @openclaw/   │ openai   │ openclaw │ enabled  │ stock:openai/index.js                                    │ 2026.5.27 │
│ openai-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ opencode │ openclaw │ disabled │ stock:opencode/index.js                                  │ 2026.5.27 │
│ opencode-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ opencode │ openclaw │ disabled │ stock:opencode-go/index.js                               │ 2026.5.27 │
│ opencode-go- │ -go      │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ openrout │ openclaw │ enabled  │ stock:openrouter/index.js                                │ 2026.5.27 │
│ openrouter-  │ er       │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ perplexi │ openclaw │ disabled │ stock:perplexity/index.js                                │ 2026.5.27 │
│ perplexity-  │ ty       │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ Phone        │ phone-   │ openclaw │ disabled │ stock:phone-control/index.js                             │           │
│ Control      │ control  │          │          │ Arm/disarm high-risk phone node commands (camera/screen/ │           │
│              │          │          │          │ writes) with an optional auto-expiry.                    │           │
│ Policy       │ policy   │ openclaw │ disabled │ stock:policy/index.js                                    │ 2026.5.27 │
│              │          │          │          │ Adds policy-backed doctor checks for workspace           │           │
│              │          │          │          │ conformance.                                             │           │
│ @openclaw/   │ qianfan  │ openclaw │ disabled │ stock:qianfan/index.js                                   │ 2026.5.27 │
│ qianfan-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ qwen     │ openclaw │ disabled │ stock:qwen/index.js                                      │ 2026.5.27 │
│ qwen-        │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ runway   │ openclaw │ disabled │ stock:runway/index.js                                    │ 2026.5.27 │
│ runway-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ searxng  │ openclaw │ disabled │ stock:searxng/index.js                                   │ 2026.5.27 │
│ searxng-     │          │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ senseaud │ openclaw │ disabled │ stock:senseaudio/index.js                                │ 2026.5.27 │
│ senseaudio-  │ io       │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ sglang   │ openclaw │ disabled │ stock:sglang/index.js                                    │ 2026.5.27 │
│ sglang-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ signal   │ openclaw │ disabled │ stock:signal/index.js                                    │ 2026.5.27 │
│ signal       │          │          │          │                                                          │           │
│ Skill        │ skill-   │ openclaw │ disabled │ stock:skill-workshop/index.js                            │ 2026.5.27 │
│ Workshop     │ workshop │          │          │ Captures repeatable workflows as workspace skills, with  │           │
│              │          │          │          │ pending review, safe writes, and skill prompt refresh.   │           │
│ @openclaw/   │ stepfun  │ openclaw │ disabled │ stock:stepfun/index.js                                   │ 2026.5.27 │
│ stepfun-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ syntheti │ openclaw │ disabled │ stock:synthetic/index.js                                 │ 2026.5.27 │
│ synthetic-   │ c        │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Talk Voice   │ talk-    │ openclaw │ disabled │ stock:talk-voice/index.js                                │           │
│              │ voice    │          │          │ Manage Talk voice selection (list/set).                  │           │
│ @openclaw/   │ tavily   │ openclaw │ enabled  │ stock:tavily/index.js                                    │ 2026.5.27 │
│ tavily-      │          │          │          │                                                          │           │
│ plugin       │          │          │          │                                                          │           │
│ @openclaw/   │ telegram │ openclaw │ enabled  │ stock:telegram/index.js                                  │ 2026.5.27 │
│ telegram     │          │          │          │                                                          │           │
│ @openclaw/   │ tencent  │ openclaw │ disabled │ stock:tencent/index.js                                   │ 2026.5.27 │
│ tencent-     │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Thread       │ thread-  │ openclaw │ disabled │ stock:thread-ownership/index.js                          │           │
│ Ownership    │ ownershi │          │          │ Prevents multiple agents from responding in the same     │           │
│              │ p        │          │          │ Slack thread. Uses HTTP calls to the slack-forwarder     │           │
│              │          │          │          │ ownership API.                                           │           │
│ @openclaw/   │ together │ openclaw │ disabled │ stock:together/index.js                                  │ 2026.5.27 │
│ together-    │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ tokenjuice   │          │ openclaw │ disabled │ stock:tokenjuice/index.js                                │ 2026.5.27 │
│              │          │          │          │ Compacts exec and bash tool results with tokenjuice      │           │
│              │          │          │          │ reducers.                                                │           │
│ @openclaw/   │ tts-     │ openclaw │ disabled │ stock:tts-local-cli/index.js                             │ 2026.5.27 │
│ tts-local-   │ local-   │          │          │                                                          │           │
│ cli          │ cli      │          │          │                                                          │           │
│ @openclaw/   │ venice   │ openclaw │ disabled │ stock:venice/index.js                                    │ 2026.5.27 │
│ venice-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ vercel-  │ openclaw │ disabled │ stock:vercel-ai-gateway/index.js                         │ 2026.5.27 │
│ vercel-ai-   │ ai-      │          │          │                                                          │           │
│ gateway-     │ gateway  │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ vllm     │ openclaw │ disabled │ stock:vllm/index.js                                      │ 2026.5.27 │
│ vllm-        │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ volcengi │ openclaw │ disabled │ stock:volcengine/index.js                                │ 2026.5.27 │
│ volcengine-  │ ne       │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ voyage   │ openclaw │ disabled │ stock:voyage/index.js                                    │ 2026.5.27 │
│ voyage-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ vydra    │ openclaw │ disabled │ stock:vydra/index.js                                     │ 2026.5.27 │
│ vydra-       │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ Web          │ web-     │ openclaw │ disabled │ stock:web-readability/index.js                           │ 2026.5.27 │
│ Readability  │ readabil │          │          │ Extract readable article content from local HTML web     │           │
│ Extraction   │ ity      │          │          │ fetch responses.                                         │           │
│ Webhooks     │ webhooks │ openclaw │ disabled │ stock:webhooks/index.js                                  │ 2026.5.27 │
│              │          │          │          │ Authenticated inbound webhooks that bind external        │           │
│              │          │          │          │ automation to OpenClaw TaskFlows.                        │           │
│ @openclaw/   │ xai      │ openclaw │ disabled │ stock:xai/index.js                                       │ 2026.5.27 │
│ xai-plugin   │          │          │          │                                                          │           │
│ @openclaw/   │ xiaomi   │ openclaw │ disabled │ stock:xiaomi/index.js                                    │ 2026.5.27 │
│ xiaomi-      │          │          │          │                                                          │           │
│ provider     │          │          │          │                                                          │           │
│ @openclaw/   │ zai      │ openclaw │ disabled │ stock:zai/index.js                                       │ 2026.5.27 │
│ zai-provider │          │          │          │                                                          │           │
│ Codex        │ codex    │ openclaw │ enabled  │ ~/.openclaw/npm/node_modules/@openclaw/codex/dist/index. │ 2026.5.27 │
│              │          │          │          │ js                                                       │           │
│              │          │          │          │ OpenClaw Codex app-server harness and model provider     │           │
│              │          │          │          │ plugin with a Codex-managed GPT catalog.                 │           │
└──────────────┴──────────┴──────────┴──────────┴──────────────────────────────────────────────────────────┴───────────┘

## OpenClaw Status
OpenClaw status

Overview
┌──────────────────────┬───────────────────────────────────────────────────────────────────────────────────────────────┐
│ Item                 │ Value                                                                                         │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────┤
│ OS                   │ linux 6.8.0-117-generic (x64) · node 22.22.2                                                  │
│ Dashboard            │ http://2.24.196.155:18789/                                                                    │
│ Tailscale exposure   │ off                                                                                           │
│ Channel              │ stable (default)                                                                              │
│ Update               │ pnpm                                                                                          │
│ Gateway              │ local · ws://127.0.0.1:18789 (local loopback) · reachable 49ms · auth password · CMD (2.24.   │
│                      │ 196.155) app 2026.5.27 linux 6.8.0-117-generic                                                │
│ Gateway self         │ CMD (2.24.196.155) app 2026.5.27 linux 6.8.0-117-generic                                      │
│ Gateway service      │ systemd user installed · enabled · running (pid 928, state active)                            │
│ Node service         │ systemd user not installed                                                                    │
│ Agents               │ 3 · no workspaces bootstrapping · sessions 37 · default main active 8m ago                    │
│ Memory               │ enabled (plugin memory-core) · not checked                                                    │
│ Plugin compatibility │ none                                                                                          │
│ Probes               │ skipped (use --deep)                                                                          │
│ Events               │ none                                                                                          │
│ Tasks                │ 0 active · 0 queued · 0 running · 50 issues · audit clean · 190 tracked                       │
│ Heartbeat            │ disabled (main), 6h (mega), 6h (volt)                                                         │
│ Sessions             │ 37 active · default gpt-5.4-mini (200k ctx) · 3 stores                                        │
└──────────────────────┴───────────────────────────────────────────────────────────────────────────────────────────────┘

Model selection
Session agent:main:dashboard:f394bb99-77ca-477e-9202-88… is pinned to openai/gpt-5.5; config primary openai/gpt-5.4-mini will apply to new/unpinned sessions.
  Configured default: openai/gpt-5.4-mini
  Session selected: openai/gpt-5.5
  Reason: session override
  Clear with: /model openai/gpt-5.4-mini or /reset
  Docs: https://docs.openclaw.ai/concepts/models#selection-source-and-fallback-behavior

Security audit
Skipped in fast status. Full report: openclaw security audit
Deep probe: openclaw status --deep

Channels
┌──────────┬─────────┬────────┬────────────────────────────────────────────────────────────────────────────────────────┐
│ Channel  │ Enabled │ State  │ Detail                                                                                 │
├──────────┼─────────┼────────┼────────────────────────────────────────────────────────────────────────────────────────┤
│ telegram │ ON      │ SETUP  │ configured; details skipped in fast status                                             │
└──────────┴─────────┴────────┴────────────────────────────────────────────────────────────────────────────────────────┘

Sessions
┌──────────────────────────────────┬────────┬─────────┬──────────────┬──────────────┬──────────────────────────────────┐
│ Key                              │ Kind   │ Age     │ Model        │ Runtime      │ Tokens                           │
├──────────────────────────────────┼────────┼─────────┼──────────────┼──────────────┼──────────────────────────────────┤
│ agent:main:dashboard:049ab042-5… │ direct │ 8m ago  │ gpt-5.5      │ OpenAI Codex │ 118k/272k (44%) · 🗄️ 99% cached  │
│ agent:mega:cron:a71c1e63-7a26-4… │ cron   │ 33m ago │ gpt-5.4-mini │ OpenAI Codex │ 15k/200k (8%) · 🗄️ 98% cached    │
│ agent:main:telegram:direct:8352… │ direct │ 36m ago │ gpt-5.4-mini │ OpenAI Codex │ 137k/272k (50%) · 🗄️ 100% cached │
│ agent:main:dashboard:f394bb99-7… │ direct │ 37m ago │ gpt-5.5      │ OpenAI Codex │ 68k/272k (25%) · 🗄️ 95% cached   │
│ agent:main:cron:7a70d419-3b8a-4… │ cron   │ 47m ago │ gpt-5.4-mini │ OpenAI Codex │ 52k/200k (26%) · 🗄️ 54% cached   │
│ agent:mega:main                  │ direct │ 2h ago  │ gpt-5.5      │ OpenAI Codex │ 69k/272k (26%) · 🗄️ 99% cached   │
│ agent:volt:main                  │ direct │ 2h ago  │ gpt-5.5      │ OpenAI Codex │ 47k/272k (17%) · 🗄️ 99% cached   │
│ agent:mega:cron:7ce9c2cb-13f3-4… │ cron   │ 2h ago  │ gpt-5.4-mini │ OpenAI Codex │ 79k/200k (40%) · 🗄️ 10% cached   │
│ agent:mega:telegram:direct:8352… │ direct │ 2h ago  │ gpt-5.5      │ OpenAI Codex │ 157k/272k (58%) · 🗄️ 100% cached │
│ agent:volt:cron:5d2c5066-5402-4… │ cron   │ 2h ago  │ gpt-5.4-mini │ OpenAI Codex │ 77k/200k (38%) · 🗄️ 99% cached   │
└──────────────────────────────────┴────────┴─────────┴──────────────┴──────────────┴──────────────────────────────────┘

FAQ: https://docs.openclaw.ai/faq
Troubleshooting: https://docs.openclaw.ai/troubleshooting
Next steps:
  Need to share?      openclaw status --all
  Need to debug live? openclaw logs --follow
  Need to test channels? openclaw status --deep

## Global npm packages
/usr/lib
├── @gongrzhe/server-gmail-autoauth-mcp@1.1.11
├── @mcinteerj/openclaw-gmail@1.7.3
├── @modelcontextprotocol/server-filesystem@2026.1.14
├── @steipete/oracle@0.9.0
├── @steipete/summarize@0.14.1
├── @tobilu/qmd@2.1.0
├── agent-browser@0.27.0
├── clawhub@0.9.0
├── corepack@0.34.6
├── mcporter@0.9.0
├── npm@10.9.7
├── openclaw@2026.5.27
├── opencode-ai@1.14.30
├── pnpm@10.33.2
└── zapier-mcp@0.0.1


## Key browser/web commands
agent-browser: /usr/bin/agent-browser
chromium: /snap/bin/chromium
chromium-browser: /usr/bin/chromium-browser
google-chrome: gh: /usr/bin/gh
qmd: /usr/bin/qmd
summarize: /usr/bin/summarize
clawhub: /usr/bin/clawhub
openclaw: /usr/bin/openclaw
mcporter: /usr/bin/mcporter
oracle: /usr/bin/oracle
