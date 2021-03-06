# UI Testing Pull Request

#### Target Time +/- 2 Hours

## Summary

You've been given a link to the following repo. You'll follow the same process
as normal to make your changes, but at the end of it, you'll submit a pull
request to merge YOUR forked copy of the code into the main repository.

---

## Setup

1. Fork this repository
   <a href="https://github.com/DevMountain/qa_v2_em_testing" target="\_blank">qa_v2_em_testing</a>.
1. Clone it to your machine.
1. Install dependencies (`npm i`)

### Important:

You'll notice this test actually defaults to a Firefox browser. If you have
Firefox installed, this _should_ work. Otherwise, you _can_ change that line of
code to use Chrome instead.

---

## Requirements

1. Search for the employees with the title "Screenshot", and save a screenshot
   of them to a new `screenshot` folder using the page object method provided.
   - As the database is shared across all testers, if someone has removed the
     employees, you can add a few more. Please be respectful in the values you
     use.
1. Move the constant, `employees` into a `.json` file. Replace the "can edit and
   delete an employee" test with a set of tests, looping through each employee
   record in the new `.json` file.
1. Look over the tests that are already there.
   - Consider the following questions:
     - Are these tests stable/will they give us false positives?
     - Do these tests miss bugs you could find manually following the same
       processes?
     - What would you change about the testing if you were given enough time?
   - Write up your answers to these questions and add them to your project as
     `answers.txt`, a text file, that you'll commit along with your code
     changes.

### Notes:

- There will be a lot of pre-existing code to leverage, so take a few minutes to
  review what is already there.
- Look over the grading rubric in Canvas if you need further clarification on
  the requirements.

---

## Submission

1. Add and commit your changes, then push them up to GitHub.
1. On GitHub, create a pull request to merge your changes into the original
   repository.
   - Add comments about your changes in the comments box.
1. Submit a link to your pull request in Canvas.

---

## Stretch

Try to implement your suggested changes/address some of the problems you
located.

---

## Solution

The `solution` branch of the `qa_v2_em_testing` repository has potential
solutions for requirements 1 and 2. Yours do not need to look exactly the same.

- You can also find an example pull request FROM the solution branch to the
  master branch
  <a href="https://github.com/DevMountain/qa_v2_em_testing/pull/1" target="\_blank">here</a>.
