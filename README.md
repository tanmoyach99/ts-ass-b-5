##  Interfaces vs Types in TypeScript

In TypeScript, both `interface` and `type` are used to define the shape of objects — but they have different  use cases.

###  Common Ground
Both can:
1. both is used for commonly for describing an object. Type can be used for other cases too.
2.both can  be used for function signatures


---

### 🔍 Key Differences

| Feature                         | `interface`                                  | `type`                                        |
|---------------------------------|----------------------------------------------|-----------------------------------------------|
| **Extending / Inheritance**     | `interface` can `extend` another interface   | `type` can use intersections (`&`)            |
| **Merging Declarations**        |  Yes — interfaces can merge                |  No — types cannot be merged                |
| **Union / Intersection Types**  | Not supported                              | Can define union (`|`) and intersection (`&`) types |
| **Primitive Aliases**           |  No — only object structures                | Yes — can alias primitives and more        |
| **Use in Classes**              |  Commonly used for class contracts         | Can also be used, but less common           |

---

###  Examples

#### Interface
```ts
interface IPerson {
  name: string;
  age: number;
}

interface IPerson extends Student  {
  id:number;
  email:string;
}

```
#### Type
```ts
type Person={
  name: string;
  age: number;
}
type Student = Person & {
   id:number;
  email:string;
};

```




##  How TypeScript Improves Code Quality and Project Maintainability?

TypeScript is a strongly typed superset of JavaScript that adds **static type checking** to the language. It helps developers write more **robust**, **scalable**, and **self-documenting** code.

---

###  Benefits to Code Quality

#### 1. **Early Error Detection**
- TypeScript catches bugs at **compile time**, not runtime.
```ts
const userName: string = 123; //  Type 'number' is not assignable to type 'string'
```
2. Strong Type Inference
Even without explicit types, TypeScript infers them, reducing unnecessary bugs.

```
let age = 25;
// age.toUpperCase(); //  Compile-time error
```

3. Safer Refactoring
When you rename variables, interfaces, or functions, TypeScript ensures updates happen safely and consistently across files.

🛠️ Benefits to Project Maintainability
1. Self-Documenting Code
Interfaces, types, and function signatures act like built-in documentation. it prevents unnecessary time wasting 

```
interface Product {
  id: number;
  title: string;
  price: number;
}
```
2. Modular & Scalable Architecture
With strong typing and module support, large teams can work on big projects with clear contracts and fewer surprises.

3. Code Reusability with Generics
Generics allow functions and classes to be written once and used with multiple types.

```
function identity<T>(value: T): T {
  return value;
}
```
4. Better Collaboration
When working in teams, TypeScript ensures that APIs and components are used correctly and predictably.


