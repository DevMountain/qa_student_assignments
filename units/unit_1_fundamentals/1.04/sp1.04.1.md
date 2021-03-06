# Use the Right Criteria

## Skills Practice Summary

Based on the prior day's conversations, you know that you'll need to up your
testing game to a higher level of polish.

You need to understand the criteria you're testing against to keep everyone up
to speed and on the ball.

ALSO - in discussing various criteria, it is a god time to remind ourselves that
testing for ONE CRITERIA at a time is frequently the best practice.

- Evaluating one criteria at a time helps us to keep focus and not lose track of
  any criteria.
  - You might end up using multiple parts of a system out of necessity, but
    slimming tests down can lead to better coverage.
- **Masking Results** is what happens when a test fails early, say, in searching
  for an item, and so managing the cart never gets checked, and no one realizes
  that you cannot remove items from the cart until much ler after the login bug
  is resolved.

## Setup

- Have the application requirements handy:
  <a target="\_blank" href="https://devmountain-qa.github.io/employee-manager/1.1_README.html">Employee
  Manager v1.1 Requirements</a>.
- Review any criteria you identified for
  <a target="\_blank" href="https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.04/sp1.03.2.html">Skills
  Practice 1.03.2</a>

## Step 1

Looking through the requirements and the criteria you've identified, make sure
that your tests in Jira include:

- At least one Test Criteria based test
  - Reviewing crystal clear & simple criteria
- At least one Acceptance Criteria based test
  - Reviewing critical customer processes
- At least one test that you've marked with its entry criteria
  - A test that checks something your team has yet to develop, specifically
    calling out what feature change will make it a viable test

<details  markdown="1"> <summary> For example... </summary>

**Based on Test Criteria** The test case
`\*Solution\* Swapping Records Mid-Edit`is a great example of a detailed test
criteria based test. It specifically checks ONE piece of the application, only
one piece of functionality.

**Based on Acceptance Criteria** A test with the following script would be a
great example of a broad Acceptance Criteria based test:

> Users need to be able to trust that changes will save appropriately. Make sure
> that the following statements are true:
>
> - A user can save a change, and it persists when navigating away and back.
> - A user can hit cancel, see their edits disappear, and no edit is saved.
> - A user can navigate away from a record mid edit, and no edit persists.

Some might consider that too broad, but as with most of QA, **it depends**.

**Gated by Entry Criteria** A test against searching for an employee record
could be have the following comment:

> **NOTE:** This test currently will **not** pass, and won't be ready to run
> until the search functionality has been added to Employee Manager. At that
> point, QA should review the test for accuracy.

You can even mark old and 'expired' or 'retired' tests with a different sort of
exit criteria

> **NOTE:** This test does not apply to current versions of Employee Manager,
> only use if checking v1.0 or earlier.

</details>

## **_Good work!_**
