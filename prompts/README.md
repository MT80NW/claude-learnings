# Prompts Library

Effective prompts for Claude interactions.

## Categories

- [Code Review](#code-review)
- [Refactoring](#refactoring)
- [Architecture](#architecture)
- [Documentation](#documentation)
- [Debugging](#debugging)

---

## Code Review

### Comprehensive Review
```
Review this code for:
1. SOLID principle violations
2. Performance issues (Unity-specific)
3. Error handling gaps
4. Naming and readability
5. Test coverage suggestions

Be specific about line numbers and provide corrected examples.
```

### Quick Check
```
Quick check this code for obvious issues. Focus on:
- Null reference risks
- Memory leaks (Unity context)
- Thread safety
```

---

## Refactoring

### Extract Method
```
Extract the logic between lines X-Y into a well-named method. 
Ensure the method:
- Has a single responsibility
- Has clear parameter names
- Returns meaningful values
- Is testable
```

### Apply Pattern
```
Refactor this code to use the [Pattern Name] pattern.
Show the before/after and explain why this improves the code.
```

---

## Architecture

### Design Review
```
Review this class/module design for Clean Architecture compliance:
1. Are dependencies pointing inward?
2. Is the domain logic isolated?
3. Are interfaces properly defined?
4. Is it testable without external dependencies?
```

### New Feature Design
```
Design a [feature name] with these requirements:
- [Requirement 1]
- [Requirement 2]

Follow Clean Architecture with Zenject DI.
Include:
1. Interface definitions
2. Class structure
3. Zenject bindings
4. Test strategy
```

---

## Documentation

### Code Documentation
```
Add XML documentation to this class/method including:
- Summary
- Parameters with descriptions
- Return value description
- Example usage
- Any exceptions that might be thrown
```

### Architecture Decision Record
```
Create an ADR for [decision]:
- Context: Why this decision is needed
- Decision: What was decided
- Consequences: What are the implications
- Alternatives: What else was considered
```

---

## Debugging

### Bug Investigation
```
Help debug this issue:
- Expected behavior: [X]
- Actual behavior: [Y]
- Reproduction steps: [steps]

Analyze the code and suggest:
1. Likely causes
2. Debug steps to verify
3. Potential fixes
```

### Performance Analysis
```
Analyze this code for performance issues in Unity:
- Check for allocations in Update/FixedUpdate
- Identify expensive operations
- Suggest optimizations with benchmarks
```

---

## How to Use

1. Copy the relevant prompt template
2. Fill in the bracketed sections
3. Add any context-specific details
4. Use with Claude Code or chat

---

*Add new effective prompts here when discovered. Use `/learn` to capture first, then promote here.*
