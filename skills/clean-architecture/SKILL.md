---
name: clean-architecture
description: |
  Clean Architecture and Domain-Driven Design patterns for Unity projects.
  Use when:
  - Structuring project architecture
  - Implementing dependency injection (Zenject)
  - Designing domain models
  - Creating services and repositories
  - Separating concerns
  Triggers: "clean architecture", "zenject", "dependency injection", "DDD", "domain model", "repository pattern"
---

# Clean Architecture Skill

Clean Architecture patterns for Unity game development with Zenject.

## Layer Structure

```
┌─────────────────────────────────────────┐
│           Presentation Layer            │
│  (MonoBehaviours, UI, Input Handling)   │
├─────────────────────────────────────────┤
│           Application Layer             │
│    (Use Cases, Services, Commands)      │
├─────────────────────────────────────────┤
│             Domain Layer                │
│  (Entities, Value Objects, Interfaces)  │
├─────────────────────────────────────────┤
│         Infrastructure Layer            │
│   (Repositories, External Services)     │
└─────────────────────────────────────────┘
```

**Key Rule:** Dependencies point inward. Domain has no external dependencies.

## Zenject Patterns

### Basic Binding
```csharp
public class GameInstaller : MonoInstaller {
    public override void InstallBindings() {
        // Interface to implementation
        Container.Bind<IFieldingService>()
            .To<FieldingService>()
            .AsSingle();
        
        // With arguments
        Container.Bind<IBallPhysics>()
            .To<BallPhysics>()
            .AsSingle()
            .WithArguments(gravity: 9.81f);
    }
}
```

### Factory Pattern with Zenject
```csharp
// Define factory interface
public interface IFielderFactory {
    IFielder Create(FielderType type, Vector3 position);
}

// Bind factory
Container.BindFactory<FielderType, Vector3, IFielder, FielderFactory>()
    .FromFactory<CustomFielderFactory>();
```

### Signal Bus for Decoupling
```csharp
// Define signal
public class BallHitSignal {
    public Vector3 Direction { get; }
    public float Power { get; }
}

// Install
SignalBusInstaller.Install(Container);
Container.DeclareSignal<BallHitSignal>();

// Fire
_signalBus.Fire(new BallHitSignal { Direction = dir, Power = power });

// Subscribe
_signalBus.Subscribe<BallHitSignal>(OnBallHit);
```

## Domain Patterns

### Entity Base Class
```csharp
public abstract class Entity<TId> {
    public TId Id { get; protected set; }
    
    public override bool Equals(object obj) {
        if (obj is not Entity<TId> other) return false;
        return Id.Equals(other.Id);
    }
    
    public override int GetHashCode() => Id.GetHashCode();
}
```

### Value Object
```csharp
public record FieldPosition(float X, float Y, float Z) {
    public static FieldPosition SlipCordon => new(10f, 0f, 5f);
    public static FieldPosition MidOn => new(-15f, 0f, 20f);
    
    public float DistanceTo(FieldPosition other) {
        return Vector3.Distance(
            new Vector3(X, Y, Z),
            new Vector3(other.X, other.Y, other.Z)
        );
    }
}
```

### Repository Interface
```csharp
public interface IRepository<TEntity, TId> where TEntity : Entity<TId> {
    TEntity GetById(TId id);
    IEnumerable<TEntity> GetAll();
    void Add(TEntity entity);
    void Update(TEntity entity);
    void Remove(TId id);
}
```

## Service Patterns

### Application Service
```csharp
public interface IFieldingService {
    void AssignFielder(FielderId id, FieldPosition position);
    void ExecuteThrow(FielderId from, FieldPosition to);
    IReadOnlyList<IFielder> GetActiveFielders();
}

public class FieldingService : IFieldingService {
    private readonly IFielderRepository _repository;
    private readonly ISignalBus _signalBus;
    
    public FieldingService(
        IFielderRepository repository,
        ISignalBus signalBus) {
        _repository = repository;
        _signalBus = signalBus;
    }
    
    // Implementation...
}
```

## Project Structure

```
Assets/
├── _Project/
│   ├── Domain/
│   │   ├── Entities/
│   │   ├── ValueObjects/
│   │   ├── Interfaces/
│   │   └── Events/
│   ├── Application/
│   │   ├── Services/
│   │   ├── UseCases/
│   │   └── Commands/
│   ├── Infrastructure/
│   │   ├── Repositories/
│   │   └── ExternalServices/
│   ├── Presentation/
│   │   ├── Views/
│   │   ├── Controllers/
│   │   └── UI/
│   └── Installers/
│       ├── GameInstaller.cs
│       └── SceneInstallers/
```

---

*This skill is updated from learnings. Run `/organize` to promote new patterns.*
