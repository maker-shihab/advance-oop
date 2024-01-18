# Advance OOP

### Recap of Basic OOP
I have used basic Object-Oriented Programming (OOP) concepts to recapitulate OOP. I've employed classes and objects, showcasing Data Abstraction, Encapsulation, Inheritance, and Polymorphism. Below is a simple JavaScript code illustrating these fundamental concepts.

```js
// Encapsulation and Abstraction
class Person {
  constructor(firstName, lastName) {
    // Encapsulation: private properties
    let _firstName = firstName;
    let _lastName = lastName;

    // abstract method
    this.getDetails_access = function () {
      return `First name is: ${_firstName}, Last name is: ${_lastName}`;
    };
  }
}

// Employee
class Employee extends Person {
  constructor(firstName, lastName, employeeId) {
    super(firstName, lastName);
    this.employeeId = employeeId;
  }

  // Polymorphism: method overriding
  displayDetails() {
    return `Employee ID: ${this.employeeId}, ${this.getDetails_access()}`;
  }
}

// Manager
class Manager extends Employee {
  constructor(firstName, lastName, employeeId, department) {
    super(firstName, lastName, employeeId);
    this.department = department;
  }

  // Polymorphism: method overriding
  displayDetails() {
    const employeeDetails = super.displayDetails() || "";
    return `Manager in ${this.department} department, ${employeeDetails}`;
  }
}

// Test Output
const person1 = new Person('Maker', 'Shihab');
// Encapsulation and Abstraction Output
console.log(person1.getDetails_access());

const employee1 = new Employee('Monayem', 'Islam', 'E123');
// Polymorphism: Accessing overridden method Output
console.log(employee1.displayDetails());

const manager1 = new Manager('Rejwanul', 'Kobir', 'M456', 'HR');
// Polymorphism: Accessing overridden method Output
console.log(manager1.displayDetails());
```

## OutPut:
PS G:\EUB\5th Semister\AdvanceOOp> node oop.js </br>
```
  First name is: Maker, Last name is: Shihab </br>
  Employee ID: E123, First name is: Monayem, Last name is: Islam </br>
  Manager in HR department, Employee ID: M456, First name is: Rejwanul, Last name is: Kobir
```
* Reference: https://github.com/maker-shihab/advance-oop
