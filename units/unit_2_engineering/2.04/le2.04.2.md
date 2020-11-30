# UI Testing

#### Target Time Limit: +/- 60 minutes

## Summary

In this exercise, you will be testing the calculator you just fixed in the
<a href="./le2.04.1.html" target="\_blank">previous exercise</a>.

## Setup

1. Make sure you still have the `qa_calculator` running; the command `npm start`
   will get it going again.
1. Also have your `qa_playground` project open.
1. In the `qa_playground` project, add a new test, `calculator.test.ts`
1. Copy the following code into that test file:
   <details markdown="1"><summary><code>calculator.test.ts</code></summary>

   ```typescript
   import { Builder, By, Capabilities, WebDriver } from "selenium-webdriver";

   const chromedriver = require("chromedriver");

   const driver: WebDriver = new Builder()
     .withCapabilities(Capabilities.chrome())
     .build();

   describe("The calculator", () => {
     beforeEach(async () => {
       driver.get("http://localhost:3000");
     });
     afterAll(async () => {
       driver.quit();
     });
     describe("does simple math", () => {
       it("can do 2+2", async () => {
         await clickButton(driver, "2");
         await clickButton(driver, "+");
         await clickButton(driver, "2");
         await clickButton(driver, "=");
         let result = await getDisplay(driver);
         // your assertion here
       });
       it("can do 5-7", async () => {
         await clickButton(driver, "5");
         await clickButton(driver, "-");
         await clickButton(driver, "7");
         await clickButton(driver, "=");
         let result = await getDisplay(driver);
         // your assertion here
       });
       it("can do 18×2", async () => {
         await clickButton(driver, "1");
         await clickButton(driver, "8");
         await clickButton(driver, "×");
         await clickButton(driver, "2");
         await clickButton(driver, "=");
         let result = await getDisplay(driver);
         // your assertion here
       });
       it("can do 75÷10", async () => {
         await clickButton(driver, "7");
         await clickButton(driver, "5");
         await clickButton(driver, "÷");
         await clickButton(driver, "1");
         await clickButton(driver, "0");
         await clickButton(driver, "=");
         let result = await getDisplay(driver);
         // your assertion here
       });
     });
     describe("does more complicated math", () => {});
   });

   /** Pass in the driver, and a string matching the button you want to click, and the button will be clicked
    * @param {WebDriver} driver the test's driver object
    * @param {string} button the text on the button to click
    * @example clickButton(driver, "=") // will click the equals button
    */
   async function clickButton(
     driver: WebDriver,
     button: string
   ): Promise<void> {
     return (
       await driver.findElement(By.xpath(`//button[text()="${button}"]`))
     ).click();
   }
   /** Pass in the driver, and get back a promise that will resolve as the displayed value
    * @param {WebDriver} driver the test's driver object
    * @returns {Promise<string>} A promised string that resolves to the text of the display
    * @example
    * getDisplay(driver).then(result=>console.log) // will log the text
    * let result = await getDisplay(driver) // will assign the text to the variable result
    */
   async function getDisplay(driver: WebDriver): Promise<string> {
     return await (await driver.findElement(By.css(".display"))).getText();
   }
   ```

   </details>

---

## Step 1: Completing Tests

There are several existing tests. You'll notice that each has a comment:

```typescript
// your assertion here
```

In these places, create an assertion to check the value of the variable
`result`. These assertions work EXACTLY the same way as the assertions we've
been doing as part of unit testing.

> If I were checking "5+10", assuming that the buttons were clicked I would
> assert: `expect(result).toBe("15")`

Complete each of the tests, replacing the assertion comments with YOUR
assertions.

## Step 2: Additional Tests

- You'll notice in each of the existing tests, there are a few function calls:
  - `clickButton(driver, button)` to click calculator buttons
  - `getDisplay(driver)` to get the calculator's displayed value
- Each time the functions are used, we also `await` the result, and the test
  functions themselves have the prefix `async`.
  - `async` and `await` are a way to handle asynchronous functionality -- more
    on that later! Just know that if we are accessing something in the UI, we
    need to wait for the browser to complete the request.

Armed with that knowledge, you can copy existing tests (the `it` blocks) to add
tests in the last `describe` block.

> ```typescript
> describe("does more complicated math", () => {
>   it("does something else", async () => {
>     // your test here
>   });
> });
> ```

Add a test to enter each of the following equations, and assert against the
reuslts:

1. 2 ÷ (-2)
1. 3.14159 × 15 × 15
1. (-22 - 5 + 12) × 200

## Stretch

Some possible stretch activities:

- Write a test that checks the display after EVERY button press.
- Write tests to check EVERY button on the UI.

## Submission

Running the solution, I have the following console output:

```
npx jest calculator
 PASS  src/solutions/2.04/calculator.test.ts (5.886 s)
  The calculator
    does simple math
      ✓ can do 2+2 (1745 ms)
      ✓ can do 5-7 (224 ms)
      ✓ can do 18×2 (242 ms)
      ✓ can do 75÷10 (274 ms)
    does more complicated math
      ✓ can do 2 ÷ -2 (223 ms)
      ✓ can do 3.14159 × 15 × 15 (461 ms)
      ✓ can do (-22 - 5 + 12) × 200 (435 ms)

Test Suites: 1 passed, 1 total
Tests:       7 passed, 7 total
Snapshots:   0 total
Time:        5.957 s, estimated 7 s
Ran all test suites matching /calculator/i
```

Yours should be similar. When ready, copy and paste your `calculator.test.ts`
into Canvas!

## Solution

See the solution version of `calculator.test.ts` in the `qa_playground`'s `2.04`
branch at the following path:
`qa_playground/src/solutions/2.04/calculator.test.ts`
