---
name: unity-patterns
description: |
  Unity game development patterns and best practices accumulated from WCC4 development.
  Use when working on Unity projects, especially:
  - Animation systems (Playable API, Animator)
  - Camera systems
  - Fielding AI and sports game mechanics
  - Performance optimization
  - UI Toolkit
  Triggers: "unity pattern", "unity best practice", "how to in unity", "unity performance"
---

# Unity Patterns Skill

Accumulated Unity development patterns from game development experience.

## Animation Patterns

### Playable API for Frame-Perfect Control
**When to use:** Need precise frame control, blending custom animations, or runtime animation manipulation.

```csharp
// Prefer Playable API over Animator.Play() for precision
PlayableGraph graph = PlayableGraph.Create();
AnimationClipPlayable clipPlayable = AnimationClipPlayable.Create(graph, clip);
AnimationPlayableOutput output = AnimationPlayableOutput.Create(graph, "Animation", animator);
output.SetSourcePlayable(clipPlayable);
graph.Play();

// Set exact time for sweetspot positioning
clipPlayable.SetTime(exactTime);
graph.Evaluate();
```

**Why:** Animator.Play() has frame delay; Playable API gives immediate control.

### Animation State Machine Pattern
[To be filled from learnings]

## Camera Patterns

### TV Broadcast Camera System
[To be filled from learnings]

## Performance Patterns

### Component Caching
**Always cache in Awake/Start:**
```csharp
// ❌ Bad - GetComponent every frame
void Update() {
    GetComponent<Rigidbody>().AddForce(Vector3.up);
}

// ✅ Good - Cache reference
private Rigidbody _rb;
void Awake() => _rb = GetComponent<Rigidbody>();
void Update() => _rb.AddForce(Vector3.up);
```

### Object Pooling
[To be filled from learnings]

## UI Patterns

### Canvas Scaler Setup
[To be filled from learnings]

---

*This skill is updated from learnings in `/learnings/`. Run `/organize` to promote new patterns here.*
