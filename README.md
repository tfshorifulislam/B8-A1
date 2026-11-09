# Problem Solving with TypeScript & OOP

This repository contains my solutions for the **Problem Solving with TypeScript & OOP** assignment.

The assignment includes eight TypeScript problems that helped me practice different concepts, including basic types, optional parameters, union types, tuples, generics, interfaces, OOP, and asynchronous programming with Promises.

Along with the coding solutions, I have also written two technical blog posts to explain some important TypeScript concepts in a simple way.

## Project Structure

```text
solutions.ts
type-vs-interface.md
any-unknown-never.md
README.md
```

## How to Run or Compile

Make sure you have [Node.js](https://nodejs.org/) installed on your system.

You can use `npx` to run the TypeScript compiler without installing it globally.

**1. Check for TypeScript errors without generating JavaScript files:**

```bash
npx tsc --noEmit solutions.ts
```

**2. Compile TypeScript into JavaScript:**

```bash
npx tsc solutions.ts
```

This will generate a `solutions.js` file in the same directory.

## Technical Blog Posts

I have also written two blogs as part of this assignment:

**1. [Type Aliases vs Interfaces in TypeScript](type-vs-interface.md)**

Explains the differences between type aliases and interfaces, including declaration merging, extending types, and when to use each.

**2. [Understanding any, unknown, and never in TypeScript](any-unknown-never.md)**

Explores how `any`, `unknown`, and `never` work in TypeScript and why choosing the right type is important for writing safer code.
