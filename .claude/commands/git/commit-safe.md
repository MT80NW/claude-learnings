---
description: Enforces safe commit workflow with mandatory changelog updates and conventional format validation
argument-hint: [commit type, e.g. "feat", "fix", "docs", or full message like "feat(screens): add transitions"]
---

# 🛑 GIT COMMIT PERMISSION: NEVER execute `git commit` without explicit user "y" confirmation. NO EXCEPTIONS. VIOLATION = BREACH OF TRUST.

## `commit-safe`

## Role
Commit orchestrator with strict validation that enforces changelog-first workflow and prevents commit violations

## Critical Rules
🚨 **MANDATORY WORKFLOW** - NO EXCEPTIONS:
1. **ALWAYS update changelog BEFORE any staging**
2. **USER controls file staging - Claude prepares documentation**
3. **ALWAYS use conventional commit format**
4. **ALWAYS ensure commit message describes the FULL scope of changes** - not just the main change
5. **ALWAYS ask for y/n confirmation** before executing `git commit` (MANDATORY - no exceptions)

## Instructions
Execute this **EXACT SEQUENCE** - no shortcuts allowed:

### Phase 1: Ultra-Detailed Changelog (MANDATORY)
1. **Analyze ALL changes** using `git diff` and `git status --short`
2. **Create comprehensive changelog** with current timestamp following AI-OPTIMIZED format (see .claude/CLAUDE-Changelog-Format.md):
   ```
   CHANGE|YYYY-MM-DD-HH:MM:SS|Brief title
   TLDR|2-3 sentence summary. What changed, why, impact.
   PROBLEM|1.Problem one 2.Problem two 3.Problem three
   SOLUTION|A.Component:implementation details B.Component:details C.Component:details
   FILE|status|path|lines|change description
   FILE|status|path|lines|change description
   ...repeat for EVERY file changed...
   CONFIG|filename|lines|change description
   ARCH|Architecture impact description (if significant)
   TEST|Testing performed and results
   BREAK|Breaking changes description (if any)
   ---
   ```

   **Format Rules** (60-70% more compact than markdown):
   - Pipe-delimited fields (easy parsing)
   - Use abbreviations: + for added, - for removed, ~ for modified
   - FILE status: NEW, MOD, DEL
   - Lines: ranges like "10-20,35,50-60"
   - Compact descriptions: "~Initialize():grant abilities from cfg"
   - See .claude/CLAUDE-Changelog-Format.md for full specification

3. **CHANGELOG FILENAME FORMAT** (CRITICAL - avoid invalid characters):
   - ✅ Use format: `YYYY-MM-DD-HH-MM-topic.md` (hyphens only)
   - ❌ NEVER use colons `:` in filenames - they're invalid on Windows
   - Example: `2025-12-17-14-30-feature-name.md` (correct)
   - Example: `2025-12-17-14:30:00-feature-name.md` (WRONG - colons!)

4. **CRITICAL RULES for Changelog Content**:
   - ✅ Include TL;DR at the top for quick scanning
   - ✅ Document EVERY file changed with specific line numbers
   - ✅ Document EVERY function/method modified
   - ✅ Include code snippets ONLY for critical/complex changes (keep minimal)
   - ✅ List ALL new files created with their purpose
   - ✅ Document ALL configuration changes
   - ✅ Keep total changelog file size under 150KB for AI backtracking
   - ❌ NO summarization of changes - document EVERYTHING
   - ❌ NO skipping "minor" changes - document EVERYTHING
   - ❌ NO vague descriptions - be specific and precise
   - ❌ NO excessive code snippets - only show essential snippets

### Phase 2: Staging + Commit Message
2. **Present files for staging and generate commit message immediately**:
   ```
   Claude: "Changelog prepared. Please stage the files you want to commit:"
   [Shows files to stage]
   [Generates commit message immediately - no waiting for "commit"]
   ```

3. **Generate commit message** using conventional format:
   ```
   <type>(<scope>): <description>

   [optional body explaining what and why]

   🤖 Generated with [Claude Code](https://claude.ai/code)

   Co-Authored-By: Claude <noreply@anthropic.com>
   ```

   **CRITICAL - Headline Priority Rule:**
   - **HEADLINE = BIGGEST CHANGE**, not the last change or most recent fix
   - Rank changes by: lines of code added > new features > architectural changes > bug fixes
   - Example: If commit adds 900-line Editor + fixes 10-line bug, headline is about the Editor
   - Bug fixes go in the body if there's a bigger feature

   **Full Scope Requirement:**
   - Commit message must accurately describe ALL changes in the commit
   - Don't just mention the main/prominent change - cover everything
   - If the commit touches multiple areas, reflect that in the message
   - Use the body section to elaborate on additional changes if needed

### Phase 3: User Approval (MANDATORY)
4. **Present commit message and ask for confirmation**:
   ```
   Ready to commit with this message:
   ---
   <type>(<scope>): <description>

   [body]
   ---
   Execute commit? (y/n)
   ```
5. **Wait for explicit "y" or "yes"** - DO NOT proceed on "n" or any other response
6. **Only after "y" confirmation**: execute `git commit -m "message"`

## Commit Type Reference
| Type | When to Use | Example |
|------|-------------|---------|
| `feat` | New functionality | `feat(screens): add smooth transitions` |
| `fix` | Bug fixes | `fix(startup): resolve initialization order` |
| `refactor` | Code restructuring | `refactor(core): simplify service injection` |
| `perf` | Performance improvements | `perf(ui): optimize canvas rendering` |
| `docs` | Documentation only | `docs(readme): update installation guide` |
| `test` | Tests added/modified | `test(screens): add transition validation` |
| `chore` | Maintenance tasks | `chore(deps): update Unity packages` |
| `style` | Formatting changes | `style: fix code formatting` |

## Validation Checklist
✅ **Before Commit:**
- [ ] Changelog updated with timestamp
- [ ] All files staged including changelog
- [ ] Commit message follows `<type>(<scope>): <description>` format
- [ ] Subject line ≤ 50 characters
- [ ] Body lines ≤ 72 characters
- [ ] Commit message describes FULL scope of all changes (not just main change)
- [ ] Asked "Execute commit? (y/n)" and received "y" confirmation

❌ **BLOCKED PATTERNS:**
- Commit without changelog update
- Missing conventional format
- Changelog not staged
- Subject line too long
- Commit message only describes partial changes (missing scope)
- Executing commit without y/n confirmation prompt

## Examples

### Standard Commit Flow
```bash
# User: "Fix the initialization bug we just worked on"
commit-safe fix

# Claude Response:
# Phase 1: Creates changelog with bug fix details
# Phase 2: Presents files to stage + generates commit message immediately
#   "Changelog prepared. Please stage files:
#    - file1.cs
#    - file2.cs
#
#   Ready to commit with this message:
#   ---
#   fix(startup): resolve service initialization order
#   ---
#   Execute commit? (y/n)"
# User: "y"
# Claude: Stages changelog + executes git commit
```

### Documentation Commit
```bash
# User: "Commit the new guidelines we created"
commit-safe docs

# Claude Response:
# Phase 1: Creates changelog with documentation changes
# Phase 2: Presents files to stage + generates commit message immediately
#   "Changelog prepared. Please stage files:
#    - GUIDE.md
#
#   Ready to commit with this message:
#   ---
#   docs(claude): add AI-optimized commit guidelines
#   ---
#   Execute commit? (y/n)"
# User: "y"
# Claude: Stages changelog + executes git commit
```

## Safety Features
🛡️ **Protection Against Common Mistakes:**
- Blocks missing changelog updates
- Validates conventional commit format
- Ensures all files are properly staged
- Requires y/n confirmation before executing commit (MANDATORY)
- Provides clear error messages for violations

## Usage Notes
- Use `/commit-safe [type]` to trigger the command
- Command will guide you through each step
- Never skips changelog step - it's mandatory
- Always waits for your explicit approval
- Follows CLAUDE-Commit-Guidelines.md exactly

**Remember**: This command exists to prevent the "oops, forgot the changelog" moments!
