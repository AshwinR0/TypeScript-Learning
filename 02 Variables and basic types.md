
### **Section 2: Variables and Basic Types**

This section covers the fundamental building blocks of the type system.

---

#### **2.1 Core Types**

*   `string`: For textual data (`"hello"`, `'world'`).
*   `number`: For all numeric values (integers and floats).
*   `boolean`: For `true` or `false` values.

#### **2.2 Declaring Variables**

You declare variables with `let` and `const`, adding a type annotation with a colon (`:`).

```typescript
let framework: string = "React";
const version: number = 18;
let isAwesome: boolean = true;
```

#### **2.3 Type Inference**

If you initialize a variable, TypeScript is smart enough to infer its type automatically. This keeps your code clean.

```typescript
let greeting = "Hello, world!"; // TypeScript infers this is a 'string'
```

*   **Senior Dev Tip:** Rely on type inference for variables whenever possible. Explicitly type function parameters and return values, and when a variable's type isn't immediately clear from its initialization.

#### **2.4 The `any` Keyword: The Escape Hatch**

`any` tells the compiler to completely opt-out of type checking for a variable.

```typescript
let something: any = "This can be anything";
something = 42; // No error
something = false; // No error
```

*   **When to use `any` (sparingly):**
    *   Working with a legacy JavaScript library that lacks type definitions.
    *   When dealing with data from an external source where the structure is truly dynamic and unknown.
    *   During a gradual migration from JavaScript to TypeScript.

*   **When NOT to use `any`:**
    *   As a lazy fix for a type error. Using `any` defeats the entire purpose of TypeScript.

*   **Analogy: The "Miscellaneous" Drawer**
    The `any` type is like that drawer where you throw random things. It's useful in a pinch, but if you put everything in there, you lose all the benefits of organization and safety.
