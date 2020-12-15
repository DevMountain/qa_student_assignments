# Built in Test Data

## Summary

It's a huge benefit for us when we can define our tests from the ground up to
use test data from other sources. It's easier, for one, but it's also simpler to
change our tests this way.

We'll be setting up a test to sign in to the **TYJA: Track Your Job
Application** app.

## Setup

1. Create a new test file, and copy in the code from the `signInTest.test.ts`
   popout below.
   - The test logic is already there except for a `signIn` method, part of your
     practice.
1. In the same folder, create a new file, `signInData.json`, and copy in the
   data in the matching popout below.

<details markdown="1"><summary><code>signInTest.test.ts</code></summary>

```typescript
import {
  Builder,
  By,
  Capabilities,
  until,
  WebDriver,
} from "selenium-webdriver";

const chromedriver = require("chromedriver");
const driver = new Builder().withCapabilities(Capabilities.chrome()).build();

class TYJA {
  driver: WebDriver;
  usernameField: By = By.name("email");
  passwordField: By = By.name("password");
  loginButton: By = By.xpath("//button[contains(text(), 'Login')]");
  header: By = By.css(".header-left-header > p");
  jobsTitle: By = By.css(".title-bar-jobs");
  url: string = "https://tyja.devmountain.com/";
  constructor(driver: WebDriver) {
    this.driver = driver;
  }
  /**
   * loads up the app's home page, and signs in using the data in the file
   * `signInData.json`, not any parameters passed in.
   */
  async signIn(): Promise<void> {
    // your code here
  }
}

describe("TYJA", () => {
  const page = new TYJA(driver);
  beforeEach(async () => {
    // loads the page and signs in
    await page.signIn();
  });
  afterAll(async () => {
    await driver.quit();
  });
  test("login defaults to the jobs page", async () => {
    // waits for the page load
    await driver.wait(until.elementLocated(page.header));
    let header = await driver.findElement(page.header);
    let jobsTitle = await driver.findElement(page.jobsTitle);
    // makes sure the right app loaded
    expect(await header.getText()).toBe("TRACK YOUR JOB APPLICATION");
    // and that the jobs page title is visible
    expect(await jobsTitle.isDisplayed()).toBeTruthy();
  });
});
```

</details>

<details markdown="1"><summary><code>signInData.json</code></summary>

```typescript
{
    "username" : "aj@devmounta.in",
    "password" : "testPass"
}
```

</details>

---

## Step 1: Import our Data

You need to import the data from `signInData.json` into your test file.

1. If your test project doesn't already have a `tsconfig.json` in it's root
   folder, you need one.
   - `tsconfig.json`
     ```json
     {
       "compilerOptions": {
         "resolveJsonModule": true
       }
     }
     ```
1. With that `tsconfig.json` in place, you can use an import statement to pull
   any json into your tests.
   ```typescript
   import * as someAlias from "filepath/file.json";
   //now someAlias is a JavaScript object/array parsed from file.json
   console.log(someAlias);
   ```
   - Apply this pattern to import `signInData.json`

---

## Step 2: Finish the `signIn()` method

Now you can use the imported data to sign into the application.

Don't forget to define the steps you need, or follow the comments to know just
what this method should do!

---

## Stretch

Try adapting this logic to log into another page, or to create data driven
iterations; like adding/editing jobs in TYJA or something similar.

---

## Solution

The solution with comments can be viewed in `solutions/2.08/signInTest.test.ts`
in the `2.08` branch of `qa_playground`.
