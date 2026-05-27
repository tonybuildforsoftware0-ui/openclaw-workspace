# LEARNINGS.md

## 2026-04-27
- AgentMail integration completed. Security webhook pending.

## 2026-05-14
- Tony wants the assistant to work silently by default and avoid approval prompts whenever possible. Use safer first-class tools, batch work, and avoid approval-sensitive shell commands unless truly necessary.
- Tony wants even less interruption: keep replies short, don’t ask for confirmation unless the action is truly blocked, and prefer doing the safe next step immediately.
- Correction: the assistant is already running on the VPS, and Tony has already installed extra tooling to improve control and understanding. Plan around the existing VPS setup instead of assuming a fresh remote install.

## 2026-05-17
- Correction: when Tony asks “do you recommend installing this?” or asks for an opinion on a repo/tool, answer with recommendation + tradeoffs first and pause before installing unless he explicitly says to install. Approval of a queued command is not a substitute for checking whether the original intent was only advice.

## 2026-05-22
- Correction: college/research and deep-thinking reply handling should stay routed to Mega, not Oboz. When Tony corrects the lane, hand off the response instead of keeping it on the routing layer.

## 2026-05-24
- Correction: Tony does not want Oboz emitting scholarship/college cron chatter or heartbeats. Those workflows should stay with Mega, and this layer should only speak up when there is a real result or blocker to report.

## 2026-05-27
- `openclaw-telegraf-metrics automation` was intermittently returning curl exit 23 because the pipeline could trip over early-terminated output. Fixing the helper to fetch into a temp file before awk filtering made the maintenance pass stable again.
