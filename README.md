# 📚 Claude Learnings Repository

A structured knowledge base for capturing, organizing, and retrieving learnings from Claude Code and software development.

## 🚀 Quick Start

```bash
# Clone or copy this repository
cd claude-learnings

# Capture a new learning
/learn

# Weekly review
/review

# Organize and consolidate
/organize
```

## 📁 Structure

```
claude-learnings/
│
├── 📋 CLAUDE.md              # Claude Code configuration
├── 📖 README.md              # This file
│
├── 🛠️ .claude/
│   ├── commands/             # Custom slash commands
│   │   ├── learn.md          # /learn - capture learnings
│   │   ├── organize.md       # /organize - organize content
│   │   ├── review.md         # /review - weekly review
│   │   └── find.md           # /find - search learnings
│   └── agents/
│       └── knowledge-curator.md
│
├── 🎯 skills/                # Custom Claude Code skills
│   ├── unity-patterns/
│   ├── csharp-best-practices/
│   └── clean-architecture/
│
├── 📝 learnings/             # Chronological entries
│   ├── 2026/
│   │   └── 01-january/
│   └── templates/
│
├── 🔄 patterns/              # Reusable patterns
│   ├── unity/
│   ├── csharp/
│   └── claude-code/
│
├── 💻 snippets/              # Code examples
│   ├── unity/
│   └── csharp/
│
├── ⚠️ mistakes/              # Lessons from failures
│
├── 💬 prompts/               # Effective prompts
│
└── 🔗 resources/             # External references
```

## 🏷️ Tagging System

### Categories
| Tag | Use For |
|-----|---------|
| `#unity` | Unity Engine, MonoBehaviour, etc. |
| `#csharp` | C# language features |
| `#claude-code` | Claude Code workflows |
| `#architecture` | Design patterns, SOLID |
| `#performance` | Optimization |
| `#testing` | Tests and QA |

### Status
| Tag | Meaning |
|-----|---------|
| `#solved` | Issue resolved |
| `#wip` | Work in progress |
| `#question` | Needs research |
| `#important` | High-value insight |

## 📅 Maintenance Schedule

| Frequency | Action | Command |
|-----------|--------|---------|
| Daily | Capture learnings | `/learn` |
| Weekly | Review & consolidate | `/review` |
| Monthly | Deep organization | `@knowledge-curator` |

## 🔧 Setup

1. Copy this repository to your preferred location
2. Open in Claude Code: `cd claude-learnings && claude`
3. Run `/init` to let Claude understand the structure
4. Start capturing learnings with `/learn`

## 📊 Progress Tracking

Track your learning journey:
- Weekly entries in `learnings/`
- Pattern count in `patterns/`
- Snippet library growth in `snippets/`

## 🤝 Integration

Reference from other projects by adding to their CLAUDE.md:
```markdown
## Knowledge Base
Reference: ~/claude-learnings for patterns and learnings
```

---

*Created for systematic knowledge capture with Claude Code*
