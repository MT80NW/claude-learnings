# Find Learnings

When the user runs /find [query], search across all learnings and present relevant results.

## Search Scope

Search through:
- `learnings/` - All chronological entries
- `patterns/` - Documented patterns
- `snippets/` - Code examples
- `mistakes/` - Failure documentation
- `prompts/` - Prompt library
- `skills/` - Skill definitions

## Search Methods

### By Keyword
```
/find animation
→ Search for "animation" in all files
```

### By Tag
```
/find #unity
→ Find all entries tagged with #unity
```

### By Date Range
```
/find --since 2026-01-01
/find --week 2
/find --month january
```

### By Category
```
/find --in patterns
/find --in snippets/unity
```

### Combined
```
/find animation #unity --in patterns
```

## Output Format

```
🔍 Search Results for: "animation"
═══════════════════════════════════════

Found 7 matches across 4 locations:

📝 Learnings (3)
─────────────────
1. [2026-01-05] Playable API for frame-perfect control
   learnings/2026/01-january/week-01.md#playable-api
   "...Using Playable API instead of Animator.Play()..."
   Tags: #unity #animation #performance

2. [2026-01-07] Animation state machine patterns  
   learnings/2026/01-january/week-01.md#state-machine
   "...Discovered cleaner way to handle animation states..."
   Tags: #unity #animation #architecture

3. [2025-12-20] Legacy animation issues
   learnings/2025/12-december/week-51.md#legacy
   "...Problems with old animation system..."
   Tags: #unity #animation #deprecated

🔄 Patterns (2)
─────────────────
4. Unity Animation Patterns
   patterns/unity/animation-patterns.md
   Comprehensive guide to animation in Unity

5. State Machine Pattern
   patterns/unity/state-machines.md
   Generic state machine for animations

💻 Snippets (1)
─────────────────
6. Playable API Template
   snippets/unity/playable-template.cs
   Ready-to-use Playable API setup

⚠️ Mistakes (1)
─────────────────
7. Animation timing bug
   mistakes/animation-timing-issue.md
   "...Never use Time.deltaTime in animation callbacks..."

═══════════════════════════════════════
```

## Interactive Mode

If search returns many results:
```
Found 15 results. Show:
1. All results
2. Only patterns
3. Only recent (last 30 days)
4. Refine search

Choice: _
```

## No Results

If nothing found:
```
🔍 No results for "quantum physics"

Suggestions:
- Check spelling
- Try broader terms
- Search by tag: /find #physics
- Browse categories: /find --list-tags
```

## Special Commands

```
/find --list-tags     → Show all used tags
/find --recent        → Last 10 entries
/find --popular       → Most cross-referenced
/find --gaps          → Entries marked #question
```
