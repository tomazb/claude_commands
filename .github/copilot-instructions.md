# Project Instructions

This repository contains reusable prompt templates and agent profiles for AI-assisted software development workflows. The templates are designed to work with both GitHub Copilot CLI and Claude Code.

## Repository Structure

- `agents/` — Agent profiles in Claude Code format (`.md` with YAML frontmatter)
- `.github/agents/` — Agent profiles in Copilot CLI format (`.agent.md`)
- `00_`–`06_` files — Original command templates (Claude Code slash commands)
- `docs/` — Reference documentation

## Conventions

- Figma-related agents (`design-reviewer`, `react-figma-engineer`) work best when Figma MCP or design context is available; otherwise, users may need to provide design specs manually
- Prompt templates use `$ARGUMENTS` as the placeholder for user input
- Agent descriptions should be concise (1-2 sentences) in frontmatter; detailed instructions go in the prompt body
- Use `gh` CLI for GitHub operations, not raw API calls, unless advanced filtering is needed
- Follow the research → plan → implement → verify workflow pattern
- Keep prompts tool-agnostic where possible so they work across AI coding assistants
