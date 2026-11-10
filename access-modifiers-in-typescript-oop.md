Access Modifiers in TypeScript OOP
Introduction
Access modifiers control where class properties and methods can be
accessed. They are important in object-oriented programming because they
help protect data and define how different parts of an application
interact. TypeScript provides public, private, and protected. It
also provides readonly to prevent reassignment after initialization.
Detailed Explanation
A public member can be accessed from anywhere. It is the default
visibility when no modifier is written.
class User {
public name: string;

constructor(name: string) {
this.name = name;
}
}

const user = new User("Rahim");
console.log(user.name);
A private member can only be accessed inside the class where it is
declared. This is useful for hiding internal data, such as a salary.
class Employee {
private salary: number;

constructor(salary: number) {
this.salary = salary;
}

getSalary(): number {
return this.salary;
}
}
A protected member can be accessed inside its class and by subclasses,
but not directly from outside.
class Person {
protected name: string;

constructor(name: string) {
this.name = name;
}
}

class Manager extends Person {
introduce(): string {
return `I am ${this.name}`;
}
}
The readonly modifier allows a property to be assigned during
declaration or in the constructor, but prevents later reassignment.
class Product {
readonly id: number;

constructor(id: number) {
this.id = id;
}
}
Conclusion
Use public for the class's accessible API, private for internal
implementation details, and protected when subclasses need access. Use
readonly for values that should not change after initialization.
Together, these modifiers make class design safer and easier to
maintain.
