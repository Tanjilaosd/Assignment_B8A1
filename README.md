# Assignment: Problem Solving with TypeScript & OOP

## File Structure

```
├── solutions.ts
├── type-vs-interface.md
├── type-narrowing.md
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

- `type-vs-interface.md` — Core differences between type aliases and interfaces, and when to choose one.
- `type-narrowing.md` — Type narrowing using `typeof`, `instanceof`, and the `in` operator.

## How to Verify

```bash
tsc --strict --noEmit solutions.ts
```

All functions have explicit parameter and return types, use no `any`, and return the exact strings and values required by the sample outputs.
