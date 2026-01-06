CHANGE|2026-01-07-03:10:00|Initial Claude Learnings Knowledge Base Setup
TLDR|Complete setup of a structured knowledge base for capturing Claude Code learnings, Unity/C# patterns, and development best practices. Includes custom slash commands, agent definitions, skill definitions, and organized directory structure.
PROBLEM|1.No centralized system to capture learnings 2.Knowledge scattered and hard to retrieve 3.No workflow for organizing and reviewing learnings
SOLUTION|A.Repository structure:organized dirs for learnings/patterns/snippets/mistakes/prompts/resources B.Custom commands:/learn /organize /review /find for workflow automation C.Skills:unity-patterns csharp-best-practices clean-architecture D.Agent:knowledge-curator for deep organization
FILE|NEW|.claude/agents/knowledge-curator.md|1-142|Knowledge management agent for organizing learnings, pattern recognition, quality curation, promotion, gap analysis
FILE|NEW|.claude/commands/find.md|1-130|/find command - search across all learnings with keyword/tag/date/category filters
FILE|NEW|.claude/commands/git/commit-safe.md|1-202|/commit-safe command - enforces changelog-first workflow with conventional commits
FILE|NEW|.claude/commands/learn.md|1-76|/learn command - capture new learnings interactively with formatting
FILE|NEW|.claude/commands/organize.md|1-102|/organize command - organize recent content, identify promotions, cross-link
FILE|NEW|.claude/commands/review.md|1-112|/review command - weekly review with statistics and pattern analysis
FILE|NEW|.claude/settings.json|1-12|Claude Code permissions for learnings repo - Read(**), Write(learnings/patterns/snippets/mistakes/prompts/**)
FILE|NEW|.gitignore|1-21|Standard ignores: .DS_Store, IDE files, local settings, temp files
FILE|NEW|CLAUDE.md|1-88|Main Claude config - repository purpose, structure, organization rules, commands, maintenance schedule
FILE|NEW|README.md|1-116|Repository readme - quick start, structure, tagging system, maintenance schedule, setup guide
FILE|NEW|learnings/2026/01-january/week-01.md|1-85|First week learning entries - repository structure setup learning
FILE|NEW|learnings/templates/weekly-template.md|1-44|Template for weekly learning files
FILE|NEW|mistakes/README.md|1-30|Mistakes category readme - purpose and format
FILE|NEW|patterns/claude-code/README.md|1-20|Claude Code patterns category readme
FILE|NEW|patterns/csharp/README.md|1-20|C# patterns category readme
FILE|NEW|patterns/unity/README.md|1-20|Unity patterns category readme
FILE|NEW|prompts/README.md|1-25|Prompts library readme
FILE|NEW|resources/bookmarks.md|1-30|External resources and bookmarks
FILE|NEW|skills/clean-architecture/SKILL.md|1-60|Clean Architecture skill definition with triggers and patterns
FILE|NEW|skills/csharp-best-practices/SKILL.md|1-60|C# Best Practices skill definition
FILE|NEW|skills/unity-patterns/SKILL.md|1-60|Unity Patterns skill definition
FILE|NEW|snippets/csharp/README.md|1-20|C# snippets category readme
FILE|NEW|snippets/unity/README.md|1-20|Unity snippets category readme
CONFIG|.claude/settings.json|1-12|Permissions for read all, write to content directories
ARCH|Establishes modular knowledge base structure: learnings (chronological), patterns (reusable), snippets (code), mistakes (failures), prompts (templates), skills (auto-activate), resources (external)
---
