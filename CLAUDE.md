# Claude Learnings Repository

Personal knowledge base for Claude Code learnings, Unity/C# patterns, and development best practices.

## Repository Purpose

This repository serves as a living knowledge base that:
- Captures daily learnings and insights
- Documents reusable patterns and solutions
- Preserves code snippets that worked well
- Records mistakes to avoid repeating them
- Stores effective prompts for Claude interactions

## Directory Structure

```
├── skills/           → Custom Claude Code skills
├── learnings/        → Chronological learning entries
├── patterns/         → Proven, reusable patterns
├── snippets/         → Working code examples
├── mistakes/         → Lessons from failures
├── prompts/          → Effective prompt library
└── resources/        → External references
```

## Organization Rules

### Adding New Content
1. **Daily learnings** → `learnings/YYYY/MM-month/week-XX.md`
2. **Proven patterns** → `patterns/{category}/`
3. **Working code** → `snippets/{category}/`
4. **Failed experiments** → `mistakes/`
5. **Good prompts** → `prompts/`

### Content Guidelines
- Always include date and context
- Use consistent tags: `#unity` `#csharp` `#claude-code` `#architecture` `#performance`
- Include "why it matters" for each learning
- Link related entries using relative paths
- Keep entries focused and actionable

## Custom Commands

| Command | Purpose |
|---------|---------|
| `/learn` | Capture a new learning interactively |
| `/organize` | Review and organize recent learnings |
| `/review` | Weekly review and consolidation |
| `/find` | Search across all learnings |

## Periodic Maintenance

### Daily (2 min)
- Use `/learn` when discovering something new
- Tag appropriately for future searchability

### Weekly (15 min)
- Run `/review` to summarize the week
- Promote valuable learnings to patterns
- Cross-link related entries

### Monthly (30 min)
- Use `@knowledge-curator` for deep organization
- Update skills with new patterns
- Archive outdated information
- Review and update this CLAUDE.md

## Tags Reference

### Categories
- `#unity` - Unity Engine related
- `#csharp` - C# language features
- `#claude-code` - Claude Code tips and workflows
- `#architecture` - Design patterns, SOLID, Clean Architecture
- `#performance` - Optimization techniques
- `#testing` - Unit tests, integration tests
- `#git` - Version control workflows

### Status
- `#solved` - Problem resolved
- `#wip` - Work in progress
- `#question` - Needs more research
- `#important` - High-value insight

## Related Projects

- WCC4 (World Cricket Championship 4) - Main game project
- Unity patterns apply directly to WCC4 development
