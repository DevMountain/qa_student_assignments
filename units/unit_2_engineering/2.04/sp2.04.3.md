# Fix a bug, pass a test.

## Summary

In `qa_playground/src/__tests__/employeeManager.test.ts`, (created in the
previous practice assignment), all of the tests should pass. At least, they
would if they were executed like they were supposed to.

---

## Failing Test

The failing test is actually _missing_ a step.

1. Find the test "A saved change persists".
1. Review the comments.
1. Review the code.
1. Add in the missing step.
   - You should be able to copy/paste it in from another test once you know
     which step is missing.
1. Save and execute the fixed test.
   - 5/5 tests should pass.

<details markdown="1"> <summary> Hint </summary>

A quick rundown of the commands used:

- `driver.findElement(By)` will locate the element that matches the `By`
  provided, so that you can do something with it
  - `<WebElement>.click()` will click on the element the method is called on.
  - `<WebElement>.clear()` will clear the specified element's value (assuming it
    is an input).
  - `<WebElement>.sendKeys(stringOrKeys)` will type the message (the value of
    `stringOrKeys` in this case) into the element the method is called on.
- `driver.wait(until)` will pause the test until the "until" is satisfied.
  - `elementIsLocated()` resolves when the element specified exists in the DOM.
  - `elementIsVisible()` resolves when the element specified is rendered and
    visible to the user.

</details>

---

## Stretch Goal: Fix Incorrectly Passing Test

One of the tests does NOT match the stated steps, even after fixing the failing
steps.

That's not to say that the test should necessarily fail, but results from an
incorrectly written test aren't going to be reliable.
