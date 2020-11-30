# Report results from existing tests

## Summary

If we run tests and don't let anyone know the results, was running the tests
worthwhile? REporting is extremely important. It is possible to have automated
tests automatically report their results. In this exercise, however, you'll be
sketching out a test summary report from some automated tests.

## Step 1

1. Create a new test in your qa_playground that has now been set up for
   automation.
   - Name it `employeeManager.test.ts`
1. Copy into it the code hidden in the expander below.

<details markdown="1"> <summary> <code> employeeManager.test.ts </code> </summary>

```typescript
import {
  Builder,
  By,
  Capabilities,
  until,
  WebDriver,
  WebElement,
  Key,
} from "selenium-webdriver";
const chromedriver = require("chromedriver");

const driver: WebDriver = new Builder()
  .withCapabilities(Capabilities.chrome())
  .build();
const bernice: By = By.name("employee1");
const marnie: By = By.name("employee2");
const phillip: By = By.name("employee3");
const nameDisplay: By = By.id("employeeTitle");
const nameInput: By = By.name("nameEntry");
const phoneInput: By = By.name("phoneEntry");
const titleInput: By = By.name("titleEntry");
const saveButton: By = By.id("saveBtn");
const cancelButton: By = By.name("cancel");
const errorCard: By = By.css(".errorCard");

describe("Employee Manager 1.2", () => {
  beforeEach(async () => {
    await driver.get(
      "https://devmountain-qa.github.io/employee-manager/1.2_Version/index.html"
    );
  });
  afterAll(async () => {
    await driver.quit();
  });
  describe("handles unsaved, canceled, and saved changes correctly", () => {
    test("An unsaved change doesn't persist", async () => {
      /*
      This test follows these steps:
      1. Open Bernice Ortiz
      2. Edit the name input
      3. Open Phillip Weaver
      4. Open Bernice Ortiz
      5. Verify the name field is the original name
    */
      await driver.findElement(bernice).click();
      await driver.wait(
        until.elementIsVisible(await driver.findElement(nameInput))
      );
      await driver.findElement(nameInput).clear();
      await driver.findElement(nameInput).sendKeys("Test Name");
      await driver.findElement(phillip).click();
      await driver.wait(
        until.elementTextContains(
          await driver.findElement(nameDisplay),
          "Phillip"
        )
      );
      await driver.findElement(bernice).click();
      await driver.wait(
        until.elementTextContains(
          await driver.findElement(nameDisplay),
          "Bernice"
        )
      );
      expect(
        await (await driver.findElement(nameInput)).getAttribute("value")
      ).toBe("Bernice Ortiz");
    });

    test("A canceled change doesn't persist", async () => {
      /*
      This test follows these steps:
      1. Open Phillip Weaver
      2. Edit the name input
      3. Click cancel
      5. Verify the name field is the original name
    */
      await driver.findElement(phillip).click();
      await driver.wait(
        until.elementIsVisible(await driver.findElement(nameInput))
      );
      await driver.findElement(nameInput).clear();
      await driver.findElement(nameInput).sendKeys("Test Name");
      await driver.findElement(cancelButton).click();
      expect(
        await (await driver.findElement(nameInput)).getAttribute("value")
      ).toBe("Phillip Weaver");
    });

    test("A saved change persists", async () => {
      /*
      This test follows these steps:
      1. Open Bernice Ortiz
      2. Edit the name input
      3. Save the change
      4. Open Phillip Weaver
      5. Open Bernice Ortiz's old record
      5. Verify the name field is the edited name
      */
      await driver.findElement(bernice).click();
      await driver.wait(
        until.elementIsVisible(await driver.findElement(nameInput))
      );
      await driver.findElement(nameInput).clear();
      await driver.findElement(nameInput).sendKeys("Test Name");
      await driver.findElement(saveButton).click();
      await driver.findElement(phillip).click();
      await driver.wait(
        until.elementTextContains(
          await driver.findElement(nameDisplay),
          "Phillip"
        )
      );
      await driver.findElement(bernice).click();
      expect(
        await (await driver.findElement(nameInput)).getAttribute("value")
      ).toBe("Bernice Ortiz");
    });
  });
  describe("handles error messages correctly", () => {
    test("shows an error message for an empty name field", async () => {
      /*
      This test follows these steps:
      1. Open Bernice Ortiz
      2. Clear the name input
      3. Save the change
      4. Verify the error is present
      */
      await driver.findElement(bernice).click();
      await driver.wait(
        until.elementIsVisible(await driver.findElement(nameInput))
      );
      await driver.findElement(nameInput).clear();
      await driver.findElement(nameInput).sendKeys(Key.SPACE, Key.BACK_SPACE);
      await driver.findElement(saveButton).click();
      await driver.wait(until.elementLocated(errorCard));
      expect(await (await driver.findElement(errorCard)).getText()).toBe(
        "The name field must be between 1 and 30 characters long."
      );
    });
    test("lets you cancel out of an error message", async () => {
      /*
      This test follows these steps:
      1. Open Bernice Ortiz
      2. Clear the name input
      3. Save the change
      4. Verify the error is present
      5. Cancel the change
      6. Verify the error is gone
      */
      await driver.findElement(bernice).click();
      await driver.wait(
        until.elementIsVisible(await driver.findElement(nameInput))
      );
      await driver.findElement(nameInput).clear();
      await driver.findElement(nameInput).sendKeys(Key.SPACE, Key.BACK_SPACE);
      await driver.findElement(saveButton).click();
      await driver.wait(until.elementLocated(errorCard));
      expect(await (await driver.findElement(errorCard)).getText()).toBe(
        "The name field must be between 1 and 30 characters long."
      );
      await driver.findElement(nameInput).sendKeys(Key.SPACE);
      await driver.findElement(saveButton).click();
      driver.wait(() => true, 500);
      expect(await driver.findElements(errorCard)).toHaveLength(0);
    });
  });
});
```

</details>

---

## Step 2

1. Save the updated file.
1. Execute the test with the command `npx jest employee`

If you named/copied the file correctly, you'll see:

- 1 failed
- 4 passed
- 5 total tests

---

## Step 3

1. Review the tests. While the syntax may not be entirely familiar (we're using
   selenium in these tests after all), you should recognize the `describe` and
   `test` blocks.
   - There are also comments in each test explaining in plain English the
     intended process.
1. Review the console results after you ran the test; it should tell you which
   test failed.

<details markdown="1"> <summary> Test failure message: </summary>

```
  ● Employee Manager 1.2 › handles unsaved, canceled, and saved changes correctly › A saved change persists

    expect(received).toBe(expected) // Object.is equality

    Expected: "Bernice Ortiz"
    Received: "Test Name"
```

</details>

---

## Step 4

Seeing what tests are executed, and what the results are, write up a simple test
summary report for the results.

---

## Solution

If you need an example test summary report, find one commented at the bottom of
the `employeeManager.test.ts` file in the `solutions/2.04` folder in the
`qa_playground`'s `2.04` branch.
