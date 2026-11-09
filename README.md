# Assignment: Problem Solving with TypeScript & OOP

## File Structure

```
├── solutions.ts
├── access-modifiers.md
├── type-hierarchy.md
└── README.md
```

## Contents

`solutions.ts` contains all 8 problem solutions in a single file:

| # | Function / Class | Concept |
|---|---|---|
| 1 | `multiplyValue` | Optional parameter with correct `undefined`/`0` handling |
| 2 | `processInput` | Union types + `typeof` narrowing |
| 3 | `formatCoordinate` | `readonly` tuple parameter |
| 4 | `concatenateArrays` | Generics with rest parameters |
| 5 | `Course`, `getPopularCourses` | Interface + array filtering |
| 6 | `pluckValues` | Generics with `K extends keyof T` |
| 7 | `Employee`, `Manager` | OOP: `protected`, `private`, inheritance |
| 8 | `validateAgeAsync` | Async `Promise<string>` with `setTimeout` |

## Blog Posts

- [access-modifiers.md](access-modifiers.md) — How `public`, `private`, `protected`, and `readonly` work in TypeScript OOP, with examples.
- [type-hierarchy.md](type-hierarchy.md) — How `any`, `unknown`, and `never` differ in TypeScript's type hierarchy, and why `unknown` is preferred over `any`.

## How to Verify

```bash
tsc --strict --noEmit solutions.ts
```

All functions have explicit parameter and return types, use no `any`, and return the exact strings and values required by the sample outputs.
