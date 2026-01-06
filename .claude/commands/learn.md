# Capture New Learning

When the user wants to capture a learning (says "I learned...", "TIL...", or uses /learn):

## Step 1: Gather Information

Ask the user for:
1. **What did you learn?** (The core insight)
2. **Context** (What situation led to this?)
3. **Category** (unity/csharp/claude-code/architecture/other)

## Step 2: Determine File Location

- Get current date
- File path: `learnings/YYYY/MM-month/week-XX.md`
- Create the file if it doesn't exist (copy from templates/weekly-template.md)

## Step 3: Format Entry

Add to the weekly file:

```markdown
---

## [YYYY-MM-DD] - [Brief Descriptive Title]

**Context:** [Situation where this came up]

**Learning:** 
[The actual insight - be specific and actionable]

**Why it matters:** 
[Impact on workflow/code quality/productivity]

**Example:** (if applicable)
```code
[Code example demonstrating the learning]
```

**Tags:** #category #status #related-tags

**Related:** 
- [Links to related learnings if any]

---
```

## Step 4: Pattern Detection

After saving, check:
- Is this similar to existing patterns in `patterns/`?
- Should this be promoted to a pattern? (Ask user if confidence is high)
- Are there related learnings to cross-link?

## Step 5: Confirmation

Show the user:
- Where the entry was saved
- Current week's learning count
- Suggestion to promote to pattern if applicable

## Example Interaction

User: /learn

Claude: "What did you learn today?"

User: "Using Playable API instead of Animator.Play() gives frame-perfect control in Unity"

Claude: "Great! What context led to this discovery?"

User: "Was working on batting animations in WCC4 and needed precise timing"

Claude: "Got it. I'll categorize this under #unity #animation. Any code example?"

[Creates entry and confirms]
