# Claude Code Patterns

Effective patterns for working with Claude Code.

## Categories

### Workflow
- [Autonomous Workflows](autonomous-workflows.md) - Ralph Wiggum, long-running tasks

### Prompting
- [Prompting Techniques](prompting-techniques.md) - Effective prompt patterns

### Configuration
- [CLAUDE.md Patterns](claude-md-patterns.md) - Configuration best practices

### Plugins
- [Plugin Usage](plugin-usage.md) - Installed plugins and their usage

## Quick Reference

| Pattern | When to Use | File |
|---------|-------------|------|
| Ralph Wiggum | Large refactors, automation | autonomous-workflows.md |
| Feature Dev | New feature development | plugin-usage.md |
| PR Review | Before merging code | plugin-usage.md |

## Installed Plugins

| Plugin | Marketplace | Command |
|--------|-------------|---------|
| ralph-wiggum | claude-plugins-official | `/ralph-loop` |
| pr-review-toolkit | claude-plugins-official | `/pr-review-toolkit:review-pr` |
| feature-dev | anthropics/claude-code | `/feature-dev` |
| architecture-design | marcioaltoe/claude-craftkit | (auto) |

---

*Patterns are promoted from learnings using `/organize`*
