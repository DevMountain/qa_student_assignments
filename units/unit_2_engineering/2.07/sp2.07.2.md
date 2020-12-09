# Use a Page Object ONLY with JSDoc for Instruction

#### Target Time +/- 30 min

## Summary

You're getting better with code in general. Copying and pasting the following
page object into a file, and automating a test is your goal; ideally, without
ever reading the page object directly, only using the intellisense popups!

## Setup

1. Create a new file in your `qa_playground` called `PracticePage.ts`
1. Copy and paste the following code into that file.

   - Please try not to read the code just yet.
   <details markdown="1"><summary> PracticePage.ts </summary>

   ```typescript
   import { By, until, WebDriver } from "selenium-webdriver";

   /**
    * PracticePage is a page object pointing to Medium.com's topic page.
    * It has methods to navigate there, to search, and to pull article titles.
    */
   export class PracticePage {
     /** the page's driver object */
     driver: WebDriver;
     /** https://medium.com/topics */
     url: string = "https://medium.com/topics";
     /** the header marking that we are on the topics page */
     header: By = By.xpath("//h1[text()='Explore topics']");
     /** the button to open the search input */
     searchButton: By = By.css('[title="Search Medium"]');
     /** the titles in the search results */
     stories: By = By.css(".graf--title");
     /**
      * @param {WebDriver} driver - the driver object the page object should interact with
      * @example
      * const page = new PracticePage(driver);
      */
     constructor(driver: WebDriver) {
       this.driver = driver;
     }
     /**
      * Will navigate to https://medium.com/topics
      * @example
      * await page.navigate();
      */
     async navigate() {
       await this.driver.get(this.url);
       await this.driver.wait(until.elementLocated(this.header));
       await this.driver.wait(
         until.elementIsVisible(await this.driver.findElement(this.header))
       );
     }
     /**
      * Will open the searchbox and input the search terms, hitting enter
      * @param {string} searchTerm - The word/phrase you want to search
      * @example
      * await page.searchStories("Test Automation");
      */
     async searchStories(searchTerm: string) {
       await click(this.driver, this.searchButton);
       await this.driver.switchTo().activeElement().sendKeys(`${searchTerm}\n`);
       await this.driver.wait(until.elementLocated(this.stories));
     }

     /**
      * Will return an array of strings; the titles that appeared as a result of
      * the user's search. Note: The titles are returned lower case.
      * @example
      * let titles = await page.getStoryTitles();
      */
     async getStoryTitles() {
       let titles = [];
       await this.driver.wait(until.elementsLocated(this.stories));
       let elements = await this.driver.findElements(this.stories);
       for (let i = 0; i < elements.length; i++) {
         titles.push(await (await elements[i].getText()).toLowerCase());
       }
       return titles;
     }
   }

   const sendKeys = async function (driver, elementBy: By, keys) {
     await driver.wait(until.elementLocated(elementBy));
     return driver.findElement(elementBy).sendKeys(keys);
   };
   const click = async function (driver, elementBy: By) {
     await driver.wait(until.elementLocated(elementBy));
     return (await driver.findElement(elementBy)).click();
   };
   ```

   </details>

1. Create a new test called `blindTest.test.ts`, and make sure to include the
   standard boilerplate.
   ```typescript
   const chromedriver = require("chromedriver");
   import { WebDriver, Builder, Capabilities } from "selenium-webdriver";
   const driver: WebDriver = new Builder()
     .withCapabilities(Capabilities.chrome())
     .build();
   ```
1. Also, import the new page object.
   ```typescript
   import { PracticePage } from "./PracticePage";
   ```
   - Mouse over `{Practice Page}` for a tooltip about the page object.

---

## Step 1 - Define the page object

If you start defining the instance of your page object,

> `const page = new PracticeP...`

you'll get a tooltip popup explaining what the constructor needs.

---

## Step 2 - Write a test

Now with the tooltip on the page object, you can see all the properties of the
page.

Using these, you should be able to write a simple test!

- If needed, at this point, you can open `PracticePage.ts` and view the comments
  there.

---

## Solution

It's in the `2.07` branch of `qa_playground`.

---

## Stretch

- Try adding more than one test!
- Do you see how it selects the search input? Can you use that elsewhere?
