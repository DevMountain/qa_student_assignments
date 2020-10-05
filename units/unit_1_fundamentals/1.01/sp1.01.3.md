## Skills Practice Summary

With the notes that you have on what should be tested
([Skills Practice 1.01.2](./sp1.01.2.md)), and a couple of examples of what has
been tested ([Skills Practice 1.01.1](./sp1.01.1.md)), it's time to do some
exploratory testing.

## Setup

- Open the
  [Employee Manager v1.0 Documentation](https://devmountain-qa.github.io/employee-manager/1.0_README.html)
- Have your notes from [Skills Practice 1.01.2](./sp1.01.2.md) handy
- Open
  [Employee Manager v1.0](https://devmountain-qa.github.io/employee-manager/1.0_Version/index.html)

## Step 1

Using your notes, spend 15 minutes or so clicking around , testing where you
think you're the most likely to find problems.

Take notes!

## Step 2

Spend a few minutes formatting your notes on additional questions or problems
found so that you can share them with a developer or the product owner. This is,
after all, where you want to your exploratory testing to lead:

- Answering questions
- Getting problems resolved

## Solution

<details> <summary> Some problems and questions you may run across... </summary>

### Bugs

- ZERO field validation. There should probably be at least some validation not
  allowing letters into phone numbers, a minimum number of characters in
  name/title, etc.
- Not _all_ IDs in the test data are positive. That could lead to some
  inconsistencies/problems in testing.
- Navigating away from unsaved changes doesn't cancel the changes.

### Questions

Most of your questions should be about formatting and user experience.

- Should there be a way to cancel out of "editing" a contact, and being in a
  "view only" mode?

Things like that.

</details>

## **_Good work!_**
