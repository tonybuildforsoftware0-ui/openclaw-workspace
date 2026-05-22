# LEARNINGS.md

## 2026-04-27
- AgentMail integration completed. Security webhook pending.

## 2026-05-14
- Tony wants the assistant to work silently by default and avoid approval prompts whenever possible. Use safer first-class tools, batch work, and avoid approval-sensitive shell commands unless truly necessary.
- Tony wants even less interruption: keep replies short, don’t ask for confirmation unless the action is truly blocked, and prefer doing the safe next step immediately.
- Correction: the assistant is already running on the VPS, and Tony has already installed extra tooling to improve control and understanding. Plan around the existing VPS setup instead of assuming a fresh remote install.

## 2026-05-17
- Correction: when Tony asks “do you recommend installing this?” or asks for an opinion on a repo/tool, answer with recommendation + tradeoffs first and pause before installing unless he explicitly says to install. Approval of a queued command is not a substitute for checking whether the original intent was only advice.
