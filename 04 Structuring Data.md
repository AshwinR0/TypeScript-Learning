
### **Section 4: Structuring Data: Objects, Type Aliases, and Interfaces**

This section explores how to define the "shape" of your data.

---

#### **4.1 Working with Objects**

You can define the structure of an object directly in a function signature.

```typescript
function printCoordinates(pt: { x: number; y: number }) {
    console.log(`The coordinate's x value is ${pt.x}`);
    console.log(`The coordinate's y value is ${pt.y}`);
}
```

*   **Bad Behavior (Excess Property Checking):** TypeScript is stricter with object literals. Passing an object with extra properties directly will cause an error, which helps catch typos.
    ```typescript
    // Error: Object literal may only specify known properties
    printCoordinates({ x: 100, y: 200, z: 300 });

    // This is OK, because the type is first widened to a new variable
    const point3D = { x: 100, y: 200, z: 300 };
    printCoordinates(point3D); // OK
    ```

#### **4.2 Type Aliases**

Use the `type` keyword to create a reusable name for any type, especially object shapes.

```typescript
type Point = {
    x: number;
    y: number;
};

function logPoint(p: Point) { /* ... */ }
```

#### **4.3 Interfaces**

Interfaces are another powerful way to define object shapes. They are very similar to type aliases but have some key differences.

```typescript
interface Person {
    name: string;
    age: number;
}
```

#### **4.4 Type Modifiers**

*   **`optional` (`?`):** Marks a property as not required.
*   **`readonly`:** Prevents a property from being changed after the object is created.

```typescript
type UserProfile = {
    readonly id: number;
    username: string;
    email?: string; // Optional property
};```

#### **4.5 Combining Types with `&` (Intersection Types)**

You can create a new type that has all the properties of existing types.

```typescript
type Person = { name: string; };
type Employee = { employeeId: number; };

type EmployedPerson = Person & Employee;

const newHire: EmployedPerson = {
    name: "Alice",
    employeeId: 123
};
```

#### **4.6 Interfaces vs. Type Aliases: The Key Differences**

| Feature | Interface | Type Alias |
| :--- | :--- | :--- |
| **Purpose** | Best for defining the shape of objects and classes. | More versatile; can define any type (unions, primitives). |
| **Extending** | Can be extended or implemented by other interfaces/classes using `extends`. | Cannot be extended in the same way. Uses `&` for intersections. |
| **Declaration Merging**| **Yes.** Can be defined multiple times and will be merged. | **No.** Cannot have duplicate names in the same scope. |

*   **Senior Dev Tip:**
    *   **Prefer `interface`** for defining object shapes. This aligns with convention and allows for extension.
    *   **Use `type`** when you need union types, tuples, or other more advanced type compositions.
