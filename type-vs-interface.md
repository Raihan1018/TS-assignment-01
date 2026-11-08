Type Aliases vs Interfaces in TypeScript: Core Differences and When to Use Them
Introduction

TypeScript provides two powerful ways to define custom types: Type Aliases and Interfaces. Both help developers describe the structure of data and improve code readability. Although they look similar, they have some important differences.

Detailed Explanation

An Interface is mainly used to define the structure of objects and classes. It describes which properties and methods an object should contain.

Example:

typescript
interface User {
    name: string;
    age: number;
}

const user: User = {
    name: "Rakib",
    age: 25
};


Interfaces support declaration merging. This means we can declare the same interface multiple times, and TypeScript combines their properties.

typescript
interface Person {
    name: string;
}

interface Person {
    age: number;
}


A Type Alias allows us to create custom names for different types, including primitives, unions, intersections, tuples, and object types.

Example:

typescript
type UserName = string;

type Status = "active" | "inactive";

type Employee = {
    name: string;
    salary: number;
};


Type aliases also support intersection types using the & operator.

typescript
type Admin = User & {
    role: string;
};


The main difference is that interfaces support declaration merging, while type aliases do not. Both support extending or combining object structures, but their syntax differs.

When Should We Use Them?

Use interfaces when defining object structures, class contracts, or public APIs that may need extension.

Use type aliases when working with unions, tuples, primitive types, or more complex type combinations.

Conclusion

Both interfaces and type aliases are important TypeScript features. Choosing between them depends on the requirements of a project. Understanding their differences helps developers write cleaner, reusable, and maintainable code.