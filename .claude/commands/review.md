# Weekly Review

When the user runs /review, generate a comprehensive weekly review.

## Step 1: Gather This Week's Data

Read:
- All entries from current week's learning file
- Any patterns created this week
- Snippets added this week
- Mistakes documented

## Step 2: Generate Statistics

Calculate:
- Total learnings this week
- Breakdown by category (#unity, #csharp, etc.)
- Comparison to previous weeks (if data exists)

## Step 3: Highlight Top Insights

Identify the 3-5 most impactful learnings based on:
- Explicit #important tags
- Length/detail of entry
- Presence of code examples
- Cross-references from other entries

## Step 4: Pattern Analysis

Look for:
- **Emerging patterns**: Topics appearing multiple times
- **Knowledge gaps**: Areas mentioned but not explored
- **Connections**: Links between different categories

## Step 5: Generate Review Document

Create `learnings/YYYY/MM-month/week-XX-review.md`:

```markdown
# Week XX Review - [Date Range]

## 📊 Statistics

| Category | Count | Trend |
|----------|-------|-------|
| Unity | 4 | ↑ |
| C# | 2 | → |
| Claude Code | 3 | ↑ |
| Architecture | 1 | ↓ |
| **Total** | **10** | |

## 🌟 Top Insights This Week

### 1. [Most Impactful Learning Title]
[Brief summary and why it matters]

### 2. [Second Learning]
[Brief summary]

### 3. [Third Learning]
[Brief summary]

## 🔄 Emerging Patterns

- **Animation Systems**: Multiple learnings about Playable API 
  → Consider creating `patterns/unity/animation-systems.md`

- **Clean Architecture in Unity**: Several DI-related entries
  → May need dedicated skill

## 🎯 Knowledge Gaps Identified

- [ ] Need to explore: [Topic mentioned but not detailed]
- [ ] Question pending: [Unresolved question from learnings]

## 📈 Progress

- Patterns created: X
- Snippets added: X
- Skills updated: X

## 🔮 Next Week Focus

Based on this week's momentum:
1. Deep dive into [emerging topic]
2. Document [frequently used pattern]
3. Explore [knowledge gap]

## 📝 Notes

[Any additional observations or meta-learnings about the learning process itself]
```

## Step 6: Suggest Actions

Prompt the user:
```
📋 Suggested Actions:

1. [ ] Promote "Playable API" learning to patterns/unity/
2. [ ] Create skill for Clean Architecture patterns
3. [ ] Research [knowledge gap topic]
4. [ ] Run /organize to consolidate

Would you like me to execute any of these?
```

## Step 7: Update Streak (Optional)

If tracking consistency:
- Note consecutive weeks with entries
- Celebrate milestones (e.g., "🎉 4 weeks of consistent learning!")
