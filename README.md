# Stellar AI Workshop Starter

A minimal starter repo for the "Building with AI on Stellar" workshop (BAF).

## The exercise (about 20 minutes)

1. Fork this repo and clone your fork.
2. Open it in Claude Code (or Cursor).
3. Run the `stellar-research` skill (type `/stellar-research` in Claude Code) and pick any Stellar project, protocol, or topic you're curious about.
4. Review the file it generates under `research/`.
5. Commit and push it to your fork.

That's it. You leave the workshop with one real commit showing an AI agent pulling live Stellar ecosystem data for you.

## Stack used

- Claude Code, as the orchestrator
- Cursor Composer, as the code-writing sub-agent (optional, only needed if you go beyond notes)
- Raven, the Stellar ecosystem AI gateway (MCP tool), for live research (SCF proposals, dev docs, SEPs/CAPs, project directory)
- A custom skill (`.claude/skills/stellar-research`) that wraps the Raven research workflow into one command

## After the workshop

Keep the fork. Swap the skill for whatever you're actually building, and point it at your own project instead of a research note.
