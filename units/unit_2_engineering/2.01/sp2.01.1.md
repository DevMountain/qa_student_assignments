# Finish Tests with Values

## Skills Practice Summary

Practicing with testing, you'll be adding in a few values to complete the tests
included in this practice assignment.

## Setup

- There are a few ways to set up to test this application:
  1. If you know how to use git/github, clone
     <a href="https://github.com/DevMountain/practiceUnitTesting_qa2.01" target="\blank">this
     repository</a>, and use the `valueTesting.test.ts` test file.
     - Then install the dependencies by using the command `npm i`.
  1. Use the testing folder you set up following along with the 2.01 examples.
     - You can skip to step 4 in the manual setup below.
  1. Follow the instructions below:

<details markdown="1"><summary>Manual setup instructions</summary>

1. Create a new folder on your computer; you can call it something like
   `practiceUnitTesting`.
1. Open that folder in VS Code.
1. With that folder as your "working directory" run the following commands:
   - `npm init -y`
   - `npm i --save-dev jest typescript ts-jest @types/jest`
   - `npx ts-jest config:init`
1. Add a new file called: `valueTesting.test.ts`
1. Copy in the code below.

```typescript
describe("value testing", () => {
  test("strings are string", () => {
    expect(/* a matching string*/).toBe("Hello World");
    expect(stringCheck(/*a word */)).toBeTruthy();
    expect(stringCheck(/*a sentence*/)).toBeTruthy();
    expect(stringCheck(/*not a string*/)).toBeFalsy();
  });
  test("numbers are numbers", () => {
    expect(/* a matching number*/).toBe(3.14159);
    expect(numberCheck(/*a decimal number*/)).toBeTruthy();
    expect(numberCheck(/*an equation*/)).toBeTruthy();
    expect(numberCheck(/*not a number*/)).toBeFalsy();
  });
  test("booleans are booleans", () => {
    expect(/* a matching boolean*/).toBe(false);
    expect(booleanCheck(/*a "true" boolean*/)).toBeTruthy();
    expect(booleanCheck(/*a "false" boolean*/)).toBeTruthy();
    expect(booleanCheck(/*not a boolean*/)).toBeFalsy();
  });
});

function numberCheck(x) {
  return typeof x == "number";
}
function stringCheck(x) {
  return typeof x == "string";
}
function booleanCheck(x) {
  return typeof x == "boolean";
}
```

</details>

</br>

## Step 1

Replace the comments in the code with valid values.

- For example:

```typescript
expect(/* a matching string*/).toBe("Hello World");
```

would become

```typescript
expect("Hello World").toBe("Hello World");
```

or

```typescript
expect(booleanCheck(/*a "true" boolean*/)).toBeTruthy();
```

could become a couple of things

```typescript
expect(booleanCheck(true)).toBeTruthy();
//or a comparison to GET a boolean value
expect(booleanCheck(3 > 2)).toBeTruthy();
```

## Step 2

Run the test by using the command `npx jest`

- You should see 1 test suite and 3/3 tests passing.

<details markdown="1"><summary><strong>Solution</strong>: <code>valueTesting.test.ts</code></summary>

```typescript
describe("value testing", () => {
  test("strings are string", () => {
    expect("Hello World").toBe("Hello World");
    expect(stringCheck("test")).toBeTruthy();
    expect(stringCheck("Coding is more fun than manual testing.")).toBeTruthy();
    expect(stringCheck(1010101010101010)).toBeFalsy();
  });
  test("numbers are numbers", () => {
    expect(3.14159).toBe(3.14159);
    expect(numberCheck(-555.333)).toBeTruthy();
    expect(numberCheck((3 * 5) / 13 + 1)).toBeTruthy();
    expect(numberCheck("12")).toBeFalsy();
  });
  test("booleans are booleans", () => {
    expect(false).toBe(false);
    expect(booleanCheck(true)).toBeTruthy();
    expect(booleanCheck(false)).toBeTruthy();
    expect(booleanCheck(5)).toBeFalsy();
  });
});

function numberCheck(x) {
  return typeof x == "number";
}
function stringCheck(x) {
  return typeof x == "string";
}
function booleanCheck(x) {
  return typeof x == "boolean";
}
```

</details>

</br>

## Stretch

- Move all of these values into typed variables!

<details markdown="1"><summary><strong>Solution</strong>: <code>valueTesting.test.ts</code></summary>

```typescript
describe("value testing", () => {
  test("strings are string", () => {
    let hello: string = "Hello World";
    let word: string = "test";
    let sentence: string = "Coding is more fun than manual testing.";
    let notAString: number = 1010101010101010;

    expect(hello).toBe("Hello World");
    expect(stringCheck(word)).toBeTruthy();
    expect(stringCheck(sentence)).toBeTruthy();
    expect(stringCheck(notAString)).toBeFalsy();
  });
  test("numbers are numbers", () => {
    let pi: number = 3.14159;
    let decimal: number = -555.333;
    let equationResults: number = (3 * 5) / 13 + 1;
    let notANumber: string = "12";

    expect(pi).toBe(3.14159);
    expect(numberCheck(decimal)).toBeTruthy();
    expect(numberCheck(equationResults)).toBeTruthy();
    expect(numberCheck(notANumber)).toBeFalsy();
  });
  test("booleans are booleans", () => {
    let isFalse: boolean = false;
    let isTrue: boolean = true;
    let falseFromComparison: boolean = 2 > 12;
    let notABoolean: number = 5;

    expect(isFalse).toBe(false);
    expect(booleanCheck(isTrue)).toBeTruthy();
    expect(booleanCheck(falseFromComparison)).toBeTruthy();
    expect(booleanCheck(notABoolean)).toBeFalsy();
  });
});

function numberCheck(x) {
  return typeof x == "number";
}
function stringCheck(x) {
  return typeof x == "string";
}
function booleanCheck(x) {
  return typeof x == "boolean";
}
```

</details>

</br>

## **_Good work!_**
