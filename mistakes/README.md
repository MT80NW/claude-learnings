# Mistakes & Lessons Learned

> "The only real mistake is the one from which we learn nothing." - Henry Ford

Document failures and mistakes to avoid repeating them.

## Format

Each entry should include:
- **Date**: When it happened
- **What went wrong**: The mistake
- **Why it happened**: Root cause
- **Impact**: What was affected
- **Lesson**: What to do instead
- **Prevention**: How to avoid in future

---

## Mistakes Log

### Template Entry

```markdown
## [YYYY-MM-DD] - [Brief Title]

**What went wrong:**
[Description of the mistake]

**Why it happened:**
[Root cause analysis]

**Impact:**
[What was affected - time lost, bugs introduced, etc.]

**Lesson:**
[What should have been done instead]

**Prevention:**
[How to avoid this in the future - checklist items, rules, etc.]

**Tags:** #category
```

---

<!-- Add mistakes below -->

## 2026-01-07 - Plugin Installation Without Marketplace Path

**What went wrong:**
Tried to install Claude Code plugin with just the plugin name, command failed silently or with unclear error.

**Why it happened:**
Assumed plugin names were globally unique like npm packages. They're not - they require marketplace context.

**Impact:**
~15 minutes debugging why plugins weren't installing.

**Lesson:**
Always use full path: `/plugin install [name]@[owner/repo]`

**Prevention:**
- Keep plugin installation guide handy
- Document installed plugins with their full paths
- Test installation commands before documenting

**Tags:** #claude-code #plugins

---
