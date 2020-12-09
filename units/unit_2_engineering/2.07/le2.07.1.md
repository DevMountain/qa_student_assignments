# Create a Page Object

#### Target Time +/- 30 minutes

## Summary

Your assignment is to create a page object that can be imported into the
following test that will make it work.

## Setup

1. Add in your `qa_playground` or another project set up for automation a new
   file, `specifications.test.ts`.
1. Copy in the code:
   <details markdown="1"> <summary><code>specifications.test.ts</code></summary>

   ```typescript
   import { SpecPage } from "./SpecPage";
   const chromedriver = require("chromedriver");
   import { WebDriver, Builder, Capabilities } from "selenium-webdriver";
   const driver: WebDriver = new Builder()
     .withCapabilities(Capabilities.chrome())
     .build();
   const page = new SpecPage(driver);

   test("it works", async () => {
     await page.navigate();
     await page.doSearch("purple");
     expect(await page.getResults()).toContain("purple");
   });
   afterAll(async () => {
     await driver.quit();
   });
   ```

   </details>

## Assignment

Create a new page object that is exported from a file named `SpecPage.ts` in the
same folder as `specifications.test.ts`.

It should allow the `specifications.test.ts` test to pass.

## Submission

Push your code up to github and submit a link to the repo. (It can be your
`qa_playgrounds` repository.)

## Solution

Check the `2.07` branch of your `qa_playground` repository.

## Stretch

Add more methods and tests!
