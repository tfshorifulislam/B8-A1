# Type Narrowing in TypeScript: typeof, instanceof, and in

## Introduction

While working with TypeScript, we sometimes need to handle values that can have more than one type. For example, a function might accept either a string or a number. But the problem is that we cannot use every operation on both types. We need to check what kind of value we are dealing with before using it. This is where type narrowing becomes useful. It helps TypeScript understand the actual type of a value inside a particular block of code.

## Detailed Discussion

The typeof operator is one of the easiest ways to narrow a type. It is mainly used to check primitive values such as strings and numbers.

```ts
function formatValue(value: string | number): string {
  if (typeof value === "string") {
    return value.toUpperCase();
  }

  return value.toFixed(2);
}
```

In this example, the function accepts either a string or a number. If the value is a string, it converts it to uppercase. Otherwise, it treats the value as a number and formats it with two decimal places.

Another useful way to narrow types is the instanceof operator. It checks whether an object belongs to a particular class. This is helpful when working with different class instances.

```ts
class Dog {
  bark() {
    return "Woof!";
  }
}

class Cat {
  meow() {
    return "Meow!";
  }
}

function makeSound(pet: Dog | Cat): string {
  if (pet instanceof Dog) {
    return pet.bark();
  }

  return pet.meow();
}
```

Here, TypeScript can identify whether the pet is a Dog or a Cat. Based on that check, we can call the correct method without getting a type error.

We can also use the in operator when working with objects that have different properties. It checks whether a particular property exists in an object.

```ts
type Admin = { name: string; permissions: string[] };
type Customer = { name: string; purchaseCount: number };

function describe(user: Admin | Customer): string {
  if ("permissions" in user) {
    return `Admin: ${user.permissions.length} permissions`;
  }

  return `Customer: ${user.purchaseCount} purchases`;
}
```

In this example, the presence of the permissions property helps TypeScript identify an Admin. Otherwise, it treats the user as a Customer.

These techniques are useful because they allow us to work with different types more safely and reduce unnecessary type assertions.

## Conclusion

Type narrowing is an important concept in TypeScript, especially when working with union types. The typeof operator is useful for primitive values, instanceof helps identify class instances, and the in operator is useful for checking object properties. Once we understand how these checks work, handling different types becomes much easier and our code becomes more reliable.