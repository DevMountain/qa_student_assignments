# Finish This Page Object

#### Target Time Limit: +/- 30 minutes

## Summary

At this point, you've worked with a few page objects. That said, you should be
able to use one comfortably; this exercise has a test with a page object
template you will need to complete for the test to pass.

## Setup

Create a new test file in your `qa_playground` to copy the following code into.
Open up the website corresponding to the page object's url property, and
complete any areas marked with a comment.

<details markdown="1"><summary><code>boardgameGeek.test.ts</code></summary>

```typescript
import {
  By,
  until,
  WebDriver,
} from "selenium-webdriver";

const driver: WebDriver = // need to build the driver

class BggPage {
  driver: WebDriver;
  url: string = "https://boardgamegeek.com/";
  headerLogo: By = // need a locator
  searchBar: By = // need a locator
  gamePageName: By = // need a locator
  gamePageRating: By = // need a locator
  constructor(driver: WebDriver) {
    this.driver = driver;
  }
  async navigate() {
    await this.driver.get(this.url);
    await this.driver.wait(until.elementLocated(this.headerLogo));
    await this.driver.wait(
      until.elementIsVisible(await driver.findElement(this.headerLogo))
    );
  }
  async getResultNameLink(name: string) {
    let xpathToFind = `//div[@id='maincontent']//a[text()='${name}']`;
    await this.driver.wait(until.elementLocated(By.xpath(xpathToFind)));
    return await this.driver.findElement(By.xpath(xpathToFind));
  }
}

const bgg = new BggPage(driver);

describe("BoardGameGeek.com", () => {
  jest.setTimeout(15000);
  beforeEach(async () => {
    await bgg.navigate();
  });
  afterAll(async () => {
    await driver.quit();
  });
  test("the page loads", async () => {
    // we need to wait for the page to load; we'll make sure the header logo is present
    await driver.wait(until.elementLocated(bgg.headerLogo));
    // now we'll make sure the header logo has the right alt text to validate that
    // the right page loaded.
    expect(await driver.findElement(bgg.headerLogo).getAttribute("alt")).toBe(
      "boardgame geek logo"
    );
  });
  test("I can search for a game and open the page", async () => {
    // again, we wait for the page to load
    await driver.wait(until.elementLocated(bgg.searchBar));
    // search with the new line character to hit enter
    await driver.findElement(bgg.searchBar).sendKeys("Gloomhaven\n");
    // use our page object method to ge the results page link for Gloomhaven
    await (await bgg.getResultNameLink("Gloomhaven")).click();
    await driver.wait(until.elementLocated(bgg.gamePageName));
    // we're just verifying the game we opened is Gloomhaven
    expect(await (await driver.findElement(bgg.gamePageName)).getText()).toBe(
      "Gloomhaven"
    );
  });
  test("terraforming mars has a better rating than apples to apples", async () => {
    // we've already tested searching for a game; we'll test faster with direct navigation
    await driver.get(
      "https://boardgamegeek.com/boardgame/167791/terraforming-mars"
    );
    await driver.wait(until.elementLocated(bgg.gamePageName));
    // once the page has loaded, we'll grab our game's rating
    let tmRating = parseFloat(
      // parseFloat will get a floating point (decimal) number out of text
      await (await driver.findElement(bgg.gamePageRating)).getText()
    );
    await driver.get("https://boardgamegeek.com/boardgame/74/apples-apples");
    await driver.wait(until.elementLocated(bgg.gamePageName));
    // same here;
    let ataRating = parseFloat(
      await (await driver.findElement(bgg.gamePageRating)).getText()
    );
    // and we're asserting the one rating value to be higher than the other
    expect(tmRating).toBeGreaterThan(ataRating);
  });
});

```

</details>

---

## Step 1

After looking at the file, you should notice that you have some errors present.

1. The `const driver:WebDriver` is undefined.
1. You're missing 4 locators.

First thing is to build your driver. You should be able to do this just fine by
copying in code from other tests if needed.

---

## Step 2

Find your locators by locating the element on the website, and devising a good
locator for each, then building the By:

1.  headerLogo
    - The BGG logo in the page's header
1.  searchBar
    - The search input in the page's header
1.  gamePageName
    - The name of the game on an individual game page
1.  gamePageRating
    - The rating of the game on an individual game page

--

## Solution

For the solution to this practice, see the `solutions` folder in the `2.06`
branch of the `qa_playground` repo.

---

## Stretch

Add some more tests! You might look for other games, browse, etc.
