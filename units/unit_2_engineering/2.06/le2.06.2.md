# Test with a page object

#### Target Time Limit: +/- 120 minutes

## Summary

Your task is to test the Todo application via automation, using a page object!

---

## Setup

Assuming you've completed the setup from the previous lab exercise, you'll be
just fine.

- If you haven't, look <a href="./le2.06.1.html" target="\blank">there</a>.

---

## Step 1

Find `todoTests.test.ts` in the `src/__tests__` folder.

- You should see an empty class, `TodoPage`, as well as some test prompts.

---

## Step 2

1. Determine what functionality you will test.
   - You do NOT need to follow the prompts already in the test file. You can
     come up with your own ideas.
   - You should not ONLY test the functionality covered in `firstTest.test.ts`.
1. Sketch an outline of the steps you'll need to follow to execute these tests.

---

## Step 3

1. Make a list of all of the elements you'll need locators for to be able to
   execute these tests.
1. Place them all as properties of the TodoPage class.

You can probably copy all of the locators from `firstTest.test.ts` to start.

---

## Step 4

Create your tests.

- You can copy and paste as needed/wanted from other tests.
- You don't need any set number of tests here; so long as you have a page object
  and some testing passing, you're good to go.

---

## Submission

Once you're ready to submit your tests, follow the steps to

1. add
1. commit
1. push

This will send your changes to your cloned GitHub repo. Submit a link to that
repository to complete the assignment in Canvas.

---

## Solution

See the `todoTests.test.ts` file in the `qa_todo_test` repo's `solution` branch.

---

## Stretch

Is there any regular functionality you could make into a function or a method?

- Attempt to make either a helper function or a page object method.

Are there any regular patterns you use that you could define as a class of its
own?

- Define a method or typescript interface for the pattern.
