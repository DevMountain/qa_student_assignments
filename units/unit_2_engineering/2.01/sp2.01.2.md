# Finish Tests with Assertions

## Skills Practice Summary

Continuing your testing practice, you'll be adding assertions instead of values.

## Setup

1. Use the folder created in the last skills practice:
   <a target="\blank" href="https://devmountain.github.io/qa_student_assignments/units/unit_2_engineering/2.01/sp2.01.1.html">Finish
   Tests with Values (SP 2.01.1)</a>.
   - If you do not already have it set up, follow the setup instructions from
     that skills practice.
   - A cloned repository will already include `assertionTesting.test.ts`,
     otherwise follow the instructions below to add it.
2. Have the [Jest Expect Docs](https://jestjs.io/docs/en/expect) handy.

<details><summary>Manual setup instructions</summary>

1. Open the folder created for
   <a target="\blank" href="https://devmountain.github.io/qa_student_assignments/units/unit_2_engineering/2.01/sp2.01.1.html">Finish
   Tests with Values (SP 2.01.1)</a>
1. Add a new file called: `assertionTesting.test.ts`
1. Copy in the code below.

```typescript
describe("testing assertions", () => {
  it("asserts on size", () => {
    const smaller: number = 5;
    const greaterOrEqual: number = 5;
    const bigger: number = 321654987;

    // Add an assertion that "smaller" is less than "bigger"

    // Add another assertion that "greaterOrEqual" is greater than or equal to "smaller"

    // Add a final assertion that "bigger" is *not* less than "smaller"
  });
  it("asserts on truth", () => {
    const hello: string = "Hello World";
    const sentence: string = "The quick brown fox jumped over the lazy dog.";

    // One of these statements is true, and one is not. Wrap each in the appropriate assertion!
    hello.includes("Hi There");
    sentence.includes("fox");
  });
  it("asserts on things being the same", () => {
    const numberCompare1: number = 3.14159;
    const numberCompare2: number = 3.14;
    const stringCompare1: string = "Hi";
    const stringCompare2: string = "Hi";

    // Add a passing assertion comparing numberCompare1 and numberCompare2 based on being equal

    // Add a passing assertion comparing stringCompare1 and stringCompare2 based on being equal
  });
});
```

</details>
</br>

## Step 1

Each "test" in the file has commented instructions. You should be able to find
an assertion in the Jest docs linked above that you can use to verify the code
appropriately.

- For example, in "asserts on size":

```typescript
const smaller: number = 5;
const greaterOrEqual: number = 5;
const bigger: number = 321654987;

// Add an assertion that "smaller" is less than "bigger"
```

would become

```typescript
const smaller: number = 5;
const greaterOrEqual: number = 5;
const bigger: number = 321654987;

// Add an assertion that "smaller" is less than "bigger"
expect(smaller).toBeLessThan(bigger);
```

or

```typescript
const smaller: number = 5;
const greaterOrEqual: number = 5;
const bigger: number = 321654987;

// Add an assertion that "smaller" is less than "bigger"
expect(smaller < bigger).toBeTruthy();
```

When in doubt try a few different assertions. The solution uses the following
list of solution:

<details><summary>Possible Assertions</summary>

- toBeLessThan
- toBeGreaterThanOrEqual
- toBeTruthy
- toBeFalsy
- toEqual
- _and_ the `.not` modifier

</details>
<br />

## Step 2

Run the test by using the command `npx jest`

- You should see 1 test suite and 3/3 tests passing.

<details><summary><strong>Solution</strong>: <code>assertionTesting.test.ts</code></summary>

```typescript
describe("testing assertions", () => {
  it("asserts on size", () => {
    const smaller: number = 5;
    const greaterOrEqual: number = 5;
    const bigger: number = 321654987;

    // Add an assertion that "smaller" is less than "bigger"
    expect(smaller).toBeLessThan(bigger);
    // Add another assertion that "greaterOrEqual" is greater than or equal to "smaller"
    expect(greaterOrEqual).toBeGreaterThanOrEqual(smaller);
    // Add a final assertion that "bigger" is *not* less than "smaller"
    expect(bigger).not.toBeLessThan(smaller);
  });
  it("asserts on truth", () => {
    const hello: string = "Hello World";
    const sentence: string = "The quick brown fox jumped over the lazy dog.";

    // One of these statements is true, and one is not. Wrap each in the appropriate assertion!
    hello.includes("Hi There");
    sentence.includes("fox");
    expect(hello.includes("Hi There")).toBeFalsy();
    expect(sentence.includes("fox")).toBeTruthy();
  });
  it("asserts on things being the same", () => {
    const numberCompare1: number = 3.14159;
    const numberCompare2: number = 3.14;
    const stringCompare1: string = "Hi";
    const stringCompare2: string = "Hi";

    // Add a passing assertion comparing numberCompare1 and numberCompare2 based on being equal
    expect(numberCompare1).not.toEqual(numberCompare2);
    // Add a passing assertion comparing stringCompare1 and stringCompare2 based on being equal
    expect(stringCompare1).toEqual(stringCompare2);
  });
});
```

</details>
</br>

## Stretch

- Compare the different values several times trying out the different assertions
  in the docs linked above!

## **_Good work!_**
