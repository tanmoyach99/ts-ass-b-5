## 📘 Interfaces vs Types in TypeScript

In TypeScript, both `interface` and `type` are used to define the shape of objects — but they have different  use cases.

### ✅ Common Ground
Both can:
1. Describe the shape of an object
2. Be used for function signatures
3. Support extension (with some differences)

---

### 🔍 Key Differences

| Feature                         | `interface`                                  | `type`                                        |
|---------------------------------|----------------------------------------------|-----------------------------------------------|
| **Extending / Inheritance**     | `interface` can `extend` another interface   | `type` can use intersections (`&`)            |
| **Merging Declarations**        | ✔️ Yes — interfaces can merge                | ❌ No — types cannot be merged                |
| **Union / Intersection Types**  | ❌ Not supported                              | ✔️ Can define union (`|`) and intersection (`&`) types |
| **Primitive Aliases**           | ❌ No — only object structures                | ✔️ Yes — can alias primitives and more        |
| **Use in Classes**              | ✔️ Commonly used for class contracts         | ✔️ Can also be used, but less common           |

---

### 🧪 Examples

#### Interface
```ts
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: string;
}

type Person = {
  name: string;
  age: number;
};

type Employee = Person & {
  employeeId: string;
};
```

