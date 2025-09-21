
### **Section 5: Collections: Arrays and Tuples**

This section covers ordered lists of data.

---

#### **5.1 Arrays**

*   **Declaration Syntax 1 (Recommended):**
    ```typescript
    let numbers: number[] = [1, 2, 3];
    ```
*   **Declaration Syntax 2 (Generic):**
    ```typescript
    let names: Array<string> = ["Alice", "Bob"];
    ```

*   **Multidimensional Arrays:**
    ```typescript
    let matrix: number[][] = [[1, 2], [3, 4]];
    ```

#### **5.2 Tuples**

Tuples are arrays with a **fixed length and known types** for each element in a specific order.

```typescript
// This tuple must have exactly 2 elements: a number then a string
let user: [number, string] = [1, "Alice"];
```

*   **When to use Tuples:** Ideal for things like returning a pair of related but different-typed values from a function.
*   **When NOT to use Tuples:** For complex data, an object with named properties is almost always more readable and maintainable (`{ id: 1, name: "Alice" }` is clearer than `[1, "Alice"]`).