# Good class design

Let's look at a class for a use that you're familiar with. Many companies want
to be able to track information about their employees. We'll talk about defining
a class for that specific use.

## Setup

Create a new file in your `qa_playground`, I'm calling mine `employee.ts`.

## Define the Class

What follows is a basic object definition for an employee like those in our
Employee Manager.

```typescript
const employee1 = {
  name: "",
  phone: "",
  email: "",
  id: "",
};
```

This works, but if we wanted to avoid needing to write out a new object for each
record, we need a class!

To define a class, follow this pattern:

```typescript
class someName {
  // class here is a key word
  property1; // properties, when undefined sit empty
  property2: boolean; // you can type them just as you'd expect
  property3: string = "test"; // you can assign a default value as well
  constructor(property1, property2: boolean) {
    // constructor is a special method to initialize an instance of the class
    // the parameters you define here are passed in when a "new" instance is made
    this.property1 = property1;
    // `this` is a keyword saying "this context"
    //  here, it refers to "this" instance of the class, so setting the
    //  properties with the values passed in
    this.property2 = property2;
  }
}

// a new instance of this class would look something like this...
let someThing = new someName(0, false);
```

**Define a class** called Employee. It should have properties and the
constructor needs parameters for:

- id: a number
- name: a string
- phoneNumber: a string
- email: a string

If you did it right, define a new instance of the class, and log it; it should
look something like this...

```
Employee {
  id: 1,
  name: 'Test Person',
  phone: '8015551234',
  email: 'test@person.com'
}
```

## Add a method

We have a working employee class now. We'll add a pretty common method,
`toString()` that will return a string formatted how we want.

Here's a pattern for adding a method (old comments cleared out for clarity's
sake).

```typescript
class someName {
  property1;
  property2: boolean;
  property3: string = "test";
  constructor(property1, property2: boolean) {
    this.property1 = property1;
    this.property2 = property2;
  }
  // a method is added simply by adding the name of the method, then standard
  // function formatting.
  toString(): string {
    // here toString takes no parameters, and returns a string
    let output =
      `This is an instance of someName... \n` +
      `\tFirst property: ${this.property1}\n` +
      `\tSecond property: ${this.property2}\n` +
      `\tThird property: ${this.property3}`;
    return output;
  }
}
let someThing = new someName(0, false);
console.log(someThing.toString());
// access a method from the instance of the object!
```

You can format your `toString()` however you want to display the employee
information.

I set mine up for the following output...

```
Employee Record --- ID: 1
Name: Test Person
Contact Information
        Phone: 8015551234
        Email: test@person.com
```

## Stretch Goals

1. Set up an array of employees to act as a directory!
1. Create a function that will accept an employee, and validate for each
   employee:
   - Name is populated
   - Id is unique and positive
   - Email is valid
   - Phone number is 10 digits

## Solution

Not including the stretch goals, your solution is in the `2.03` branch of the
`qa_practice` repository.
