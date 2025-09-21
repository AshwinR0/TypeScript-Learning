
### **Section 6: Advanced & Specialized Types**

This section covers more powerful and specific type constructs.

---

#### **6.1 Union Types (`|`)**

A union type allows a variable to be one of several types. Use the pipe (`|`) character to separate the types.

```typescript
let id: string | number;
id = 101;    // OK
id = "101";  // OK
```

*   **Union Narrowing:** You must check the type of a union variable before you can use methods specific to that type. This is called "narrowing."
    ```typescript
    function printId(id: string | number) {
        if (typeof id === "string") {
            // Here, TypeScript knows 'id' is a string
            console.log(id.toUpperCase());
        } else {
            // Here, TypeScript knows 'id' is a number
            console.log(id);
        }
    }
    ```

#### **6.2 Literal Types**

You can use specific values as types. This is incredibly powerful when combined with union types to limit a variable to a set of known strings or numbers.

```typescript
type Status = "success" | "error" | "pending";

let currentStatus: Status;
currentStatus = "success"; // OK
currentStatus = "failed";  // Error: Type '"failed"' is not assignable to type 'Status'.
```

#### **6.3 Enums**

Enums (enumerations) allow you to define a set of named constants.

*   **Numeric Enums (default):** Values auto-increment from 0.
    ```typescript
    enum Direction {
        Up,    // 0
        Down,  // 1
        Left,  // 2
        Right  // 3
    }
    const myDirection = Direction.Up; // 0
    ```

*   **String Enums (more readable):** Each member must be initialized with a string.
    ```typescript
    enum LogLevel {
        Info = "INFO",
        Warning = "WARNING",
        Error = "ERROR"
    }
    const logLevel = LogLevel.Error; // "ERROR"
    ```