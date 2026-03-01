# AI Dev Commands

Reusable prompt templates and agent profiles for AI-assisted software development. Works with both **GitHub Copilot CLI** and **Claude Code**.

## Quick Start

### GitHub Copilot CLI

The `.github/agents/` directory contains agent profiles that Copilot CLI discovers automatically:

```bash
# Launch Copilot CLI in this repo
copilot

# Browse available agents
/agent

# Or reference an agent directly in your prompt
Use the issue-analyzer agent to plan work for issue #42
```

Available agents via `/agent`:

| Agent | What it does |
|-------|-------------|
| `codebase-researcher` | Reverse-engineers codebases to extract architecture patterns |
| `design-reviewer` | Verifies UI implementations match Figma designs |
| `design-iterator` | Iteratively refines UI components through screenshot-analyze-implement cycles |
| `prompt-engineer` | Creates and optimizes system prompts for AI agents |
| `react-figma-engineer` | Translates Figma designs into React/Tailwind components |
| `experiment-driven-dev` | Implements changes through iterative experiment logs |
| `codebase-context-generator` | Generates `llms.txt` documentation files for a codebase |
| `issue-analyzer` | Analyzes GitHub issues and creates implementation plans |
| `issue-creator` | Creates well-structured GitHub issues at flexible detail levels |
| `pr-comment-resolver` | Systematically resolves all PR review comments |
| `marketing-writer` | Crafts marketing content from actual code changes |

### Claude Code

The `agents/` directory and numbered command files (`01_`–`06_`) use Claude Code's format:

```bash
# Use as slash commands (copy to .claude/commands/)
cp 01_experiment_driven_development.md .claude/commands/experiment.md

# Or reference agents directly
# (agents/ directory is auto-discovered by Claude Code)
```

## Repository Structure

```
├── .github/
│   ├── copilot-instructions.md          # Repo-wide Copilot CLI instructions
│   └── agents/                          # Copilot CLI agent profiles (.agent.md)
├── agents/                              # Claude Code agent profiles
├── docs/
│   └── claude-capabilities.md           # Claude Code capabilities reference
├── 01_experiment_driven_development.md  # Command: iterative development
├── 02_generate_codebase_context.md      # Command: generate llms.txt
├── 03_analyze_github_issue.md           # Command: plan issue implementation
├── 04_create_github_issue.md            # Command: create structured issues
├── 05_resolve_pr_comments.md            # Command: resolve PR feedback
└── 06_help_me_market.md                 # Command: marketing content
```

## Commands Reference

| # | Command | Use for |
|---|---------|---------|
| 01 | Experiment-Driven Development | Complex features, unclear bugs, performance work |
| 02 | Generate Codebase Context | Onboarding docs, AI context files, pre-refactoring analysis |
| 03 | Analyze GitHub Issue | Issue assessment, implementation planning |
| 04 | Create GitHub Issue | Feature requests, bug reports, architecture proposals |
| 05 | Resolve PR Comments | Code review feedback, pre-merge cleanup |
| 06 | Marketing Writer | Product updates, feature announcements |

## Agent Profiles

The five agents in `agents/` (Claude Code) have corresponding ports in `.github/agents/` (Copilot CLI). Six additional agents — converted from the numbered command files — are available only in Copilot CLI format.

| Agent | Claude Code | Copilot CLI | Specialty |
|-------|:-----------:|:-----------:|-----------|
| Codebase Researcher | ✅ | ✅ | Architecture analysis and reverse-engineering |
| Design Implementation Reviewer | ✅ | ✅ `design-reviewer` | Figma-to-code accuracy verification |
| Design Iterator | ✅ | ✅ | Progressive UI refinement |
| Prompt Engineer | ✅ | ✅ | System prompt creation and optimization |
| React Figma UI Engineer | ✅ | ✅ `react-figma-engineer` | Figma-to-React component implementation |
| Experiment-Driven Dev | — | ✅ | Iterative experiment-log development |
| Codebase Context Generator | — | ✅ | llms.txt documentation generation |
| Issue Analyzer | — | ✅ | GitHub issue analysis and planning |
| Issue Creator | — | ✅ | Structured GitHub issue authoring |
| PR Comment Resolver | — | ✅ | PR review feedback resolution |
| Marketing Writer | — | ✅ | Product feature marketing content |

## Best Practices

1. Select the right agent or command for your task type
2. Provide complete context when using templates
3. Follow all phases in multi-step workflows
4. Run tests and linting after changes
5. Use the research → plan → implement → verify pattern

## Contributing

When adding templates:
- Add both Copilot CLI (`.github/agents/*.agent.md`) and Claude Code (`agents/*.md`) versions
- Keep descriptions concise in frontmatter; detailed instructions go in the prompt body
- Use `$ARGUMENTS` as the placeholder for user input in command files
- Test with the target AI assistant before submitting

## Customization

- Adapt templates to match team conventions
- For Copilot CLI: copy `.github/agents/` into your project's `.github/agents/`
- For Claude Code: copy `agents/` and command files into `.claude/commands/`
- Combine agents for complex workflows