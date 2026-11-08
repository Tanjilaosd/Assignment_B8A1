# Type Aliases vs Interfaces in TypeScript: Key Differences and When to Use Each

## Introduction

TypeScript offers two main tools for naming custom types: the `type` alias and the `interface`. Both can describe the shape of an object, so beginners often treat them as interchangeable. However, they differ in syntax, capabilities, and intent. Understanding these differences helps you write cleaner, more predictable code and choose the right tool on the first try.

## Detailed Body

A type alias names any type, including primitives, unions, tuples, and mapped types. An interface only describes object shapes and class contracts. For example:

```typescript
type Status = "active" | "inactive";          // union alias
type Pair = [string, number];                 // tuple alias

interface User {
  id: number;
  name: string;
}
```

Both support extension. Interfaces use `extends`, while aliases use intersections:

```typescript
interface Admin extends User { permissions: string[] }
type Admin2 = User & { permissions: string[] }
```

Interfaces have one special advantage: declaration merging. If you declare the same interface twice, TypeScript merges the members automatically, which is useful for augmenting library types. Type aliases cannot merge and will throw a duplicate identifier error. Interfaces also tend to produce clearer error messages and better autocomplete because they appear as named entities in tooling.

Type aliases win when you need unions, tuples, conditional types, or mapped types, since interfaces cannot represent those. Prefer interfaces for object and class contracts that may be extended or augmented later. Prefer aliases for primitive-like or composite type expressions.

## Conclusion

Neither tool is universally better. Use `interface` for open, extendable object shapes and `type` for everything else. Knowing this split keeps your code idiomatic and avoids awkward refactors later.
