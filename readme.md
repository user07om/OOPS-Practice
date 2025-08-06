# THERE ARE FOUR PILLERS OF OOPS
    - Inheritance  -> parrent child relationshipt
    - Polymorphism  -> one to many, method overiding and overloading (overloading not support in js)
    - Encapsulation -> public, private keywords
    - Abstraction -> Abstract the class - and use it to extend the logic on various places.

in this repo we'll cover all those topics along with examples in js langauge mostly ts.
ts support most of the OOPS concepts.


---

# **Object-Oriented Programming (OOP) in TypeScript**

OOP is a programming paradigm based on the concept of **objects** that contain **data** (fields) and **behavior** (methods). There are **four main pillars** of OOP:

---

## ✅ **1. Inheritance**

Inheritance is the mechanism that allows a class (child) to inherit properties and methods from another class (parent).
**Purpose:** Reusability and hierarchical classification.

**Example in TypeScript:**

```typescript
class Animal {
    eat() {
        console.log("Eating...");
    }
}

class Dog extends Animal {
    bark() {
        console.log("Barking...");
    }
}

const dog = new Dog();
dog.eat();  // from Animal
dog.bark(); // from Dog
```

---

## ✅ **2. Polymorphism**

Polymorphism means **"many forms"**. It allows the same method to behave differently based on the object that calls it.
In TypeScript, polymorphism is achieved through **method overriding**.
*(Note: Method overloading as in Java/C# is not natively supported in JavaScript, but TypeScript allows function overload signatures.)*

**Example:**

```typescript
class Shape {
    area(): number {
        return 0;
    }
}

class Circle extends Shape {
    constructor(private radius: number) {
        super();
    }

    area(): number {
        return Math.PI * this.radius * this.radius;
    }
}

const shape: Shape = new Circle(5);
console.log(shape.area()); // Polymorphic behavior
```

---

## ✅ **3. Encapsulation**

Encapsulation is about **bundling data and methods** inside a class and **restricting direct access** to some components.
We achieve this using **access modifiers** like `public`, `private`, and `protected`.

**Example:**

```typescript
class BankAccount {
    private balance: number;

    constructor(initialBalance: number) {
        this.balance = initialBalance;
    }

    deposit(amount: number) {
        this.balance += amount;
    }

    getBalance() {
        return this.balance;
    }
}

const account = new BankAccount(1000);
account.deposit(500);
console.log(account.getBalance()); // 1500
// account.balance = 99999; ❌ Not allowed
```

---

## ✅ **4. Abstraction**

Abstraction hides **implementation details** and exposes only the **essential features**.
In TypeScript, we use **abstract classes** or **interfaces** to achieve this.

**Example:**

```typescript
abstract class Payment {
    abstract process(amount: number): void;
}

class CreditCardPayment extends Payment {
    process(amount: number): void {
        console.log(`Processing credit card payment of $${amount}`);
    }
}

const payment: Payment = new CreditCardPayment();
payment.process(100);
```

---

## ✅ **Why TypeScript for OOP?**

TypeScript supports:

* **Classes** and **Interfaces**
* **Access Modifiers** (`public`, `private`, `protected`)
* **Abstract Classes**
* **Generics**
* **Static Types** (making OOP more robust)

---

### ✅ Next in this repo:

* Detailed examples for each concept
* Common design patterns implemented in TypeScript
* LLD & HLD practices based on real-world scenarios

---

🔥 Do you want me to **also add a section for Design Principles (SOLID) + examples in TypeScript**?
Or **include popular Design Patterns (Singleton, Factory, Observer, etc.) with implementation**?
Or **both as part of the repo structure**?
