# Test with selectors

#### Target Time Limit: +/- 60 minutes

## Summary

Your task is to complete a test by supplying the selectors required.

---

## Setup

First, you'll want to fork and clone the `qa_todo_test` repo:

- <a href="https://github.com/DevMountain/qa_todo_test" target="\blank">https://github.com/DevMountain/qa_todo_test</a>

Once forked and cloned, don't forget to install dependencies:

- `npm i`

---

## Step 1

Find `firstTest.test.ts` in the `src/__tests__` folder, and review what is
there.

You should see the test written out with the steps explained:

> 1. Load the page
> 1. Add a todo
> 1. Find all the todos
> 1. Filter them to get any that match our test todo
> 1. We should only have the one
> 1. Mark it complete
> 1. Clear complete todos
> 1. Get the todos and filter again
> 1. We should have no matching todos

> #### Note: While this test does a few things you may not have before (chiefly working with `findElements` and `filter`), they're both pretty simple, and the test is doing it for you.

---

## Step 2

You should also see 5 `By` constants, all initialized to `null`.

You need to complete these.

<details> <summary> Hint </summary>

For `todoLabel` and `todoComplete`, you can look in the test and see that the
test is looking for these elements FROM the todo element, so we only need a
unique selector from the `li.todo` element.

</details>

---

## Submission

Don't worry about submitting this lab exercise by itself, as you'll continue on
to `todoTests.test.ts` for the next lab exercise.

---

## Solution

The solution to this exercise is in the `qa_todo_test` repo's `solution` branch.

---

## Stretch

Add additional assertions that would be useful to a quick test like this.
