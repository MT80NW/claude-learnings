# Dashboard Command

Generate a comprehensive overview of the entire knowledge base.

## Instructions

When the user runs `/dashboard`, create a DASHBOARD.md file in the repository root with a complete overview of all knowledge.

### Steps

1. **Scan the entire repository** for all .md files in:
   - `learnings/` (all years, months, weeks)
   - `patterns/` (all categories)
   - `snippets/` (all categories)
   - `mistakes/`
   - `prompts/`
   - `skills/`
   - `resources/`

2. **Generate DASHBOARD.md** with these sections:

```markdown
# 📊 Knowledge Base Dashboard
Generated: [current date/time]

## 📈 Stats
- Total Learnings: [count]
- Total Patterns: [count]
- Total Snippets: [count]
- Total Mistakes: [count]
- Total Prompts: [count]
- Skills: [count]

## 🏷️ Tags
[List all unique tags found, grouped by frequency]

## 📅 Recent Learnings (Last 14 Days)
[List recent learnings with dates and one-line summaries]

## 📚 All Learnings by Category

### Unity
- [learning title] - [date] - [file link]
...

### C#
...

### Claude Code
...

### Architecture
...

## 🧩 Patterns

### Unity Patterns
- [pattern name]: [one-line description]
...

### C# Patterns
...

### Claude Code Patterns
...

## 📝 Snippets

### Unity
- [snippet name]
...

### C#
...

## ⚠️ Mistakes Log
- [mistake title] - [date] - [status: solved/wip]
...

## 💬 Prompts Library
- [prompt name]: [category]
...

## 🎯 Skills
- [skill name]: [trigger keywords]
...

## 📖 Resources & Bookmarks
[List all bookmarked resources]

## 🕳️ Knowledge Gaps
[Areas with few or no entries that might need attention]
```

3. **After generating**, display:
   - Summary of what was found
   - Path to DASHBOARD.md
   - Suggest opening it: `open DASHBOARD.md` or `cat DASHBOARD.md`

### Options

- `/dashboard` - Generate full dashboard
- `/dashboard --quick` - Stats and recent only (faster)
- `/dashboard --category unity` - Focus on one category

### Notes

- Overwrite existing DASHBOARD.md each time
- Use relative links so clicking works in VS Code / GitHub
- Extract titles from ## headers in learning files
- Count entries by looking for `## ` headers in weekly files
