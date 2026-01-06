# Organize Learnings

When the user runs /organize, perform a comprehensive organization of recent content.

## Step 1: Scan Recent Content

Read all entries from:
- Last 2 weeks of `learnings/` files
- Any unorganized content in root folders
- Recent additions to `mistakes/` and `prompts/`

## Step 2: Analyze Themes

Identify:
- **Common themes** across learnings (e.g., multiple Unity animation entries)
- **Recurring patterns** that should be documented
- **Related entries** that should be cross-linked
- **Contradictions** that need resolution

## Step 3: Identify Promotions

Find candidates for:

### Patterns (→ `patterns/`)
Learnings that:
- Have been validated multiple times
- Are reusable across projects
- Solve a common problem

### Snippets (→ `snippets/`)
Code that:
- Works correctly
- Is self-contained
- Would be useful to copy-paste

### Skills (→ `skills/`)
Knowledge that:
- Forms a cohesive topic
- Would benefit from auto-activation
- Is frequently referenced

## Step 4: Present Summary

Show the user:

```
📊 Organization Summary
═══════════════════════════════════════

📝 Scanned: X learnings from [date range]

🏷️ Themes Detected:
   • Unity Animation (4 entries)
   • Clean Architecture (3 entries)
   • Claude Code workflows (2 entries)

📤 Promotion Candidates:
   
   → Patterns:
     • "Playable API for frame-perfect animations" 
       [learnings/2026/01/week-01.md → patterns/unity/]
     
   → Snippets:
     • "Zenject binding template"
       [learnings/2026/01/week-02.md → snippets/csharp/]

🔗 Cross-links to Add:
   • Link week-01 entry #3 to patterns/unity/animation-patterns.md
   
⚠️ Issues Found:
   • Duplicate entries about X (suggest merge)
   • Outdated reference in patterns/csharp/old-pattern.md

═══════════════════════════════════════
```

## Step 5: Execute Actions

Ask user which actions to perform:
1. **Promote patterns** - Move and format as pattern docs
2. **Extract snippets** - Copy code to snippets folder
3. **Add cross-links** - Update related entries
4. **Merge duplicates** - Consolidate similar entries
5. **Archive outdated** - Move old content to archive

## Step 6: Update Indexes

After changes:
- Update any affected SKILL.md files
- Update category index files if they exist
- Log organization actions in `learnings/organization-log.md`

## Output

Create a brief report:
```
✅ Organization Complete
   • 2 patterns created
   • 3 snippets extracted  
   • 5 cross-links added
   • 1 duplicate merged
```
