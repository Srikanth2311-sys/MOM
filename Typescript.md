# 📘 TypeScript Basics – Quick Reference

## 🔷 What is TypeScript?

TypeScript is a **superset of JavaScript** that adds **static typing**. While JavaScript is dynamically typed by default, TypeScript enables developers to catch errors at compile time.

---

## ⚙️ Installation & Setup

```bash
npm install typescript --save-dev
```

To compile a TypeScript file:

```bash
npx tsc ./with-typescript.ts
```

This will generate a corresponding `.js` file.

To initialize a TypeScript project with a config file:

```bash
npx tsc --init
```

This creates a `tsconfig.json` file for project-wide settings.

---

## 🧱 Basic Types

```ts
// Primitive types
let x: number;
let y: string;
let z: boolean;

// Special types
let a: any;
let b: unknown;
let c: void;
let d: never;

// Arrays
let hobbies: string[];

// Objects
let person2: { name: string; age: number };

// Array of objects
let people: { name: string; age: number }[];
```

---

## 🧠 Type Inference

TypeScript automatically infers types based on assigned values:

```ts
let name = "Sarika"; // inferred as string
```

---

## 🔗 Union Types

```ts
let value: string | number;
```

---

## 🏷️ Type Aliases

```ts
type Person = { name: string; age: number };

let person: Person;
let people: Person[];
```

---

## 🧮 Functions

```ts
function add_ts(a: number, b: number) {
  return a + b; // return type inferred as number
}

function printOutput(value: any): void {
  console.log(value);
}
```

---

## 🧬 Generics

```ts
function insertAtBeginning<T>(array: T[], value: T): T[] {
  const newArray = [value, ...array];
  return newArray;
}

const demoArray = [1, 2, 3];
const updatedArray = insertAtBeginning(demoArray, -1);
// updatedArray[0].split(''); // ❌ Error: number doesn't have split()

const stringArray = insertAtBeginning(['a', 'b', 'c'], 'd');
stringArray[0].split(''); // ✅ Works: string[]
```

---

## 🏫 Classes

```ts
class Student {
  constructor(
    public firstName: string,
    public lastName: string,
    public age: number,
    private courses: string[]
  ) {}

  enrol(courseName: string) {
    this.courses.push(courseName);
  }

  listCourses() {
    return this.courses.slice(); // returns a copy
  }
}

const student = new Student('Srikanth', 'Sarika', 32, ['Angular']);
student.enrol('React');
console.log(student.listCourses());
```

---

## 👤 Interfaces

Interfaces define object shapes and can be implemented by classes.

```ts
interface Human {
  firstName: string;
  age: number;
  greet: () => void;
}

let srikanth: Human = {
  firstName: 'Srikanth',
  age: 32,
  greet() {
    console.log('Hello');
  }
};

srikanth.greet();
```

---

## 👨‍🏫 Interface with Class

```ts
class Instructor implements Human {
  constructor(public firstName: string, public age: number) {}

  greet() {
    console.log('Hello from Instructor');
  }
}

const instructor = new Instructor('Max', 32);
instructor.greet();
```

---

## ✅ Summary

- TypeScript enhances JavaScript with static typing.
- Use `npx tsc` to compile `.ts` files.
- Leverage type inference, aliases, generics, and interfaces for clean, safe code.
- Use `npx tsc --init` to configure your project with a `tsconfig.json`.

---


