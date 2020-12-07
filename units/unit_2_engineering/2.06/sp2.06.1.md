# Fix Broken Locators

#### Target Time Limit: +/- 30 minutes

## Summary

You've realized that a bunch of your test might be broken because you don't have
the right selectors.

## Visit Employee Manager

Here is a list of Bys; they're all broken, and each needs fixing.

- [Employee Manager v1.2](https://devmountain-qa.github.io/employee-manager/1.2_Version/index.html)

```typescript
const pageTitle: By = By.id("titleText");
const employees: By = By.xpath("li");
const footer: By = By.name("footer");
const noEmployeeMessage: By = By.css("#noEmployee");
const employeeCardBigName: By = By.xpath('p[@id="employeeTitle"]]');
```

## Solutions

There are a number of diffferent selectors you could get for each of the above.
There are good ways to find selectors - if you want to see some good options,
check out these:

1. [Devhints - CSS](http://www.devhints.io/css)
2. [Devhints - XPath](http://www.devhints.io/xpath)

Here are some examples of possible selectors.

<details markdown="1"> <summary> Possible Solutions </summary>

```typescript
const pageTitle: By = By.id("titleText");
/*
This one is broken, because titleText is the element's class, not its id.
".titleText" is an option for CSS, or "titleText" for class.
XPath is probably a little too much work; those above are pretty simple
You could also go by text using XPath "//span[contains(text(), 'Employee Manager')]"
Or even a path based option, "//div[@class='titleBar']/span"
*/
const employees: By = By.xpath("li");
/*
You might not want a selector that will find every employee in the list, but you can
iterate through them that way, so it could work. That said, li is the tag name
- By.css("li")
- By.xpath("//li")
If there were any other unordered lists in the page though, it might not be the best option.
You can get all the li's that have a name containing 'employee' with an xpath selector
- By.xpath("//li[contains(@id, 'employee')]")
*/
const footer: By = By.name("footer");
/*
For this element, footer is both the tag AND the class - but not the name
- By.css("footer")
- By.css(".footer")
- By.class("footer")
*/
const noEmployeeMessage: By = By.css("#noEmployee");
/*
This was a trick question "#noEmployee" is a great css selector using the ID.
You could also go for
- By.id("noEmployee")
*/
const employeeCardBigName: By = By.xpath('p[@id="employeeTitle"]]');
/*
This is ALMOST a good XPath selector. You need `//` at the start of an xpath.
- By.xpath('//p[@id="employeeTitle"]')
But a simple selector using the id is probably even easier.
- By.id("employeeTitle")
- By.css("#employeeTitle")
*/
```

</details>
