
### **Section 3: Functions in TypeScript**

This section focuses on how TypeScript enhances JavaScript functions.

---

#### **3.1 Typing Function Parameters & Return Values**

You add type annotations to parameters and specify the function's return type after the parameter list.

*   **Normal Function:**
    ```typescript
    function add(x: number, y: number): number {
        return x + y;
    }
    ```*   **Arrow Function:**
    ```typescript
    const subtract = (x: number, y: number): number => {
        return x - y;
    };
    ```

#### **3.2 Default Parameters**

TypeScript infers the type from the default value, making your code more concise.

```typescript
function greet(name: string = "Guest") { // 'name' is inferred as string
    console.log(`Hello, ${name}!`);
}
```

#### **3.3 Special Return Types**

*   **`void`:** Use `void` when a function does not return any value.
    ```typescript
    function logMessage(message: string): void {
        console.log(message);
    }
    ```

*   **`never`:** Use `never` for a function that *never* completes its execution. This means it either throws an error or enters an infinite loop.
    ```typescript
    function throwError(message: string): never {
        throw new Error(message);
    }
    ```*   **Senior Dev Tip:** Understanding the difference between `void` and `never` is key. `void` means "returns nothing," while `never` means "never returns."
