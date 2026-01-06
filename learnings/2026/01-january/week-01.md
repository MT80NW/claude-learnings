# Week 01 - January 2026

> Week of January 6 to January 12, 2026

## Summary

- **Total Learnings:** 2
- **Categories:** #claude-code, #unity
- **Key Theme:** Getting started with Claude Code plugins

---

## Learnings

---

## 2026-01-07 - Claude Code Plugin Installation Syntax

**Context:** Setting up Claude Code plugins for the first time, encountered issues with installation commands.

**Learning:** 
Plugin installation requires the full marketplace path. The syntax is:
```
/plugin install [plugin-name]@[marketplace-owner/marketplace-repo]
```

Not just `/plugin install [plugin-name]` which will fail.

**Why it matters:** 
Saves debugging time when setting up new development environments. Proper syntax ensures plugins install correctly on first try.

**Example:**
```bash
# ❌ Wrong - will fail
/plugin install architecture-design

# ✅ Correct - full path
/plugin install architecture-design@marcioaltoe/claude-craftkit
```

**Tags:** #claude-code #plugins #setup #solved

**Related:** 
- Claude Code Plugins Guide document

---

## 2026-01-07 - Ralph Wiggum for Autonomous Coding Loops

**Context:** Learning about Claude Code plugins for Unity game development workflow.

**Learning:** 
Ralph Wiggum plugin creates persistent iteration loops where Claude works on tasks repeatedly until completion. Key parameters:
- `--max-iterations`: Safety limit (always set this!)
- `--completion-promise`: String that signals task is done

The plugin uses a Stop hook to intercept exit attempts and re-feed the original prompt.

**Why it matters:** 
Enables overnight automation for large refactoring tasks. Can run while away from computer.

**Example:**
```bash
/ralph-loop "Refactor all Manager classes to implement interfaces. Output <promise>DONE</promise> when complete." --max-iterations 15 --completion-promise "DONE"
```

**Tags:** #claude-code #plugins #automation #important

**Related:** 
- patterns/claude-code/autonomous-workflows.md (to be created)

---

## End of Week Notes

### Patterns Identified
- Claude Code plugin ecosystem is extensive
- Multiple marketplaces available (official, community)

### Questions to Explore
- How to create custom Claude Code plugins?
- Best practices for CLAUDE.md in Unity projects?

### To Promote to Patterns
- Plugin installation syntax → prompts/claude-code-setup.md
