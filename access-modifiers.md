
## Access Modifiers in TypeScript OOP

# Introduction
Access modifiers control where class properties and methods can be
accessed. In TypeScript object-oriented programming, the main modifiers
are `public, private, and protected`. The readonly modifier is
also useful because it prevents a property from being reassigned after
initialization.

 # Public
A public member can be accessed from anywhere: inside the class, from
a subclass, or through an object instance. It is the default access
level when no modifier is written.

``` typescript
class User {
  public name: string;

  constructor(name: string) {
    this.name = name;
  }
}

const user = new User("Mina");
console.log(user.name);
```

# Private
A private member can only be accessed inside the class where it is
declared. It cannot be accessed directly from outside that class or from
a subclass.

``` typescript
class BankAccount {
  private balance = 1000;

  getBalance(): number {
    return this.balance;
  }
}
```

```typescript
class Student {
  private age: number = 20;

  showAge(): number {
    return this.age;
  }
}

const student = new Student();

console.log(student.showAge()); // 20 

```
The getBalance() method provides controlled access to the private
property.

# Protected
A protected member is accessible inside its class and its subclasses,
but not directly through an external object.

``` typescript
class Animal {
  protected sound = "Unknown";
}

class Dog extends Animal {
  makeSound() {
    return this.sound;
  }
}
```

# Readonly
The readonly modifier allows a property to be assigned during
declaration or in the constructor, but prevents reassignment afterward.

``` typescript
class Product {
  readonly id: number;

  constructor(id: number) {
    this.id = id;
  }
}
```
# Conclusion
Access modifiers improve encapsulation and help organize class
responsibilities. Use public for accessible members, private for
internal details, protected for inheritance, and readonly for values
that should not be reassigned.

