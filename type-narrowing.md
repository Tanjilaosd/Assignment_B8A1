# Type Narrowing in TypeScript: Practical Examples with typeof, instanceof, and the in Operator

## Introduction

Type narrowing is the process of transforming a broad type into a more specific one based on runtime checks. It is what allows TypeScript to safely access properties on union types without unsafe casts. The compiler analyzes your control flow and narrows the type inside each branch, giving you both safety and good autocompletion.

## Detailed Body

The `typeof` operator narrows primitive unions. Inside a function that accepts `string | number | boolean`, each `typeof` check isolates one member:

```typescript
function processInput(value: string | number | boolean): string | number {
  if (typeof value === "string") return value.trim().toLowerCase();
  if (typeof value === "number") return value * 10;
  return value ? "Active" : "Inactive";
}
```

Because the final branch has only `boolean` left, no extra check is required.

The `instanceof` operator narrows class hierarchies. Given a union `Employee | Manager`, writing `if (x instanceof Manager)` tells TypeScript that `x` is a `Manager`, so subclass-only members become accessible.

The `in` operator narrows object unions by checking property existence:

```typescript
interface Bird { fly(): void }
interface Fish { swim(): void }

function move(animal: Bird | Fish): void {
  if ("fly" in animal) animal.fly();
  else animal.swim();
}
```

Each check must happen at runtime; TypeScript only trusts real code paths, not comments or variable annotations. Discriminated unions, using a literal `kind` field, are a fourth common technique that works especially well with switch statements.

## Conclusion

Type narrowing replaces many unsafe `any` casts with verifiable runtime checks. Master `typeof`, `instanceof`, and `in`, and your union types become both flexible and fully type-safe.
