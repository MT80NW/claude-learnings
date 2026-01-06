---
name: csharp-best-practices
description: |
  Modern C# language features and best practices for Unity and .NET development.
  Use when:
  - Designing classes or interfaces
  - Applying SOLID principles
  - Using modern C# features (records, pattern matching, etc.)
  - Writing async code
  - Optimizing with Span<T>/Memory<T>
  Triggers: "c# pattern", "solid principle", "design pattern", "modern c#", "async pattern"
---

# C# Best Practices Skill

Modern C# patterns and SOLID principles for game development.

## SOLID Principles

### Single Responsibility Principle (SRP)
**Each class should have only one reason to change.**

```csharp
// ❌ Bad - Multiple responsibilities
public class Player {
    public void Move() { }
    public void SaveToFile() { }
    public void PlaySound() { }
}

// ✅ Good - Separated responsibilities
public class PlayerMovement { public void Move() { } }
public class PlayerDataPersistence { public void Save() { } }
public class PlayerAudio { public void PlaySound() { } }
```

### Open/Closed Principle (OCP)
**Open for extension, closed for modification.**

```csharp
// Use interfaces and inheritance
public interface IDamageCalculator {
    float Calculate(float baseDamage);
}

public class CriticalDamage : IDamageCalculator {
    public float Calculate(float baseDamage) => baseDamage * 2f;
}
```

### Liskov Substitution Principle (LSP)
[To be filled from learnings]

### Interface Segregation Principle (ISP)
[To be filled from learnings]

### Dependency Inversion Principle (DIP)
**Depend on abstractions, not concretions.**

```csharp
// ✅ Good - Depends on interface
public class BattingController {
    private readonly IAnimationService _animation;
    
    public BattingController(IAnimationService animation) {
        _animation = animation;
    }
}
```

## Modern C# Features

### Records for Immutable Data
```csharp
// Perfect for DTOs and value objects
public record BallTrajectory(Vector3 Start, Vector3 End, float Speed);

// With expressions for modifications
var modified = trajectory with { Speed = 150f };
```

### Pattern Matching
```csharp
// Switch expressions
string GetFielderAction(FielderState state) => state switch {
    FielderState.Idle => "Wait",
    FielderState.Chasing => "Run",
    FielderState.Throwing => "Throw",
    _ => "Unknown"
};

// Property patterns
if (player is { Health: > 0, IsActive: true }) {
    // Player is alive and active
}
```

### Nullable Reference Types
```csharp
#nullable enable

public class FieldingManager {
    private IFielder? _activeFielder;
    
    public void AssignFielder(IFielder fielder) {
        _activeFielder = fielder ?? throw new ArgumentNullException(nameof(fielder));
    }
}
```

## Async Patterns

### ConfigureAwait in Libraries
```csharp
// In library code, avoid capturing context
public async Task<Data> LoadAsync() {
    var result = await _service.FetchAsync().ConfigureAwait(false);
    return result;
}
```

### Cancellation Tokens
```csharp
public async Task ProcessAsync(CancellationToken ct = default) {
    while (!ct.IsCancellationRequested) {
        await DoWorkAsync(ct);
    }
}
```

## Design Patterns

### Factory Pattern
[To be filled from learnings]

### Strategy Pattern
[To be filled from learnings]

### Observer Pattern (Events)
[To be filled from learnings]

---

*This skill is updated from learnings. Run `/organize` to promote new patterns.*
