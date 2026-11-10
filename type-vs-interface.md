Type Alias vs Interface in TypeScript
Introduction
TypeScript provides two important ways to describe the shape of data:
type aliases and interface. Both help developers define clear
contracts and catch mistakes before code runs. Although they often look
similar, they have different capabilities and are useful in different
situations.
Detailed Explanation
An interface is mainly used to describe the structure of objects and
classes. For example:
interface User {
name: string;
age: number;
}

const user: User = {
name: "Rahim",
age: 25,
};
A type alias can describe an object too:
type User = {
name: string;
age: number;
};
Both examples provide the same type-checking benefit. However, type
aliases are more flexible because they can represent unions,
intersections, primitive types, tuples, and function types.
type ID = string | number;

type Admin = User & {
role: "admin";
};
Interfaces support extension through extends:
interface Admin extends User {
role: "admin";
}

Another difference is declaration merging. If the same interface is
declared more than once, TypeScript combines its properties. Type
aliases cannot be reopened in this way.
Conclusion
Choose an interface when defining object shapes that may be extended or
implemented by classes. Choose a type alias when you need unions,
intersections, or other complex type expressions. In everyday object
modelling, either can work; consistency and the requirements of the
project should guide the choice.
