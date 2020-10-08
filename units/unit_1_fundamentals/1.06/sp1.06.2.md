# Maintain Your Tests

## Skills Practice Summary

As will happen regularly with testing, our application has been updated,
including updates to requirements. It's time to look at what _existing_
functionality has changed, and make some decisions about our testing.

## Setup

- Have your tests for Employee Manager available.
- Open the requirements for
  [Employee Manager v1.2](https://devmountain-qa.github.io/employee-manager/1.2_README.html).
- Also open the
  [Employee Manager v1.2 application](https://devmountain-qa.github.io/employee-manager/1.2_Version/index.html).

## Step 1

Review the new requirements once again. What has changed in alreay existing
functionality?

- If necessary you can open the
  [v1.1 requirements](https://devmountain-qa.github.io/employee-manager/1.1_README.html)
  for direct comparison.

Do the same with the application - do you see any other changes?

- Having different versions side by side can make it easier to spot changes;
  here is the link for the
  [v1.1 application](https://devmountain-qa.github.io/employee-manager/1.1_Version/index.html).

Take notes of changes to the **existing functionality** as well as any new
functionality you may have missed in doing
[Skills Practice 1.05.1](./sp1.05.1.md).

<details> <summary> Solution </summary>

Your list might have more/less detail, but should roughly capture: **Documented
changes (In the requirements)**

- Error message updates
- You can fix input and save after getting an error **Changes I noticed**
- You can create a scrollable list of employees

</details>

## Step 2

Now you'll need to review your existing test cases. Which ones need to be
updated?

- You don't always _need_ to update a test that checks tweaked functionality.
  - Your test might have correctly checked functionality, and the changes
    include a fix that allow your test to pass!
  - Your test was broad enough not to include the fine detail.
- If your tests are broad enough not to require an update, you might still want
  to add a note or comment with a link to the updated requirements, such that a
  tester will not assume a change means a bug.

Make a list!

## Step 3

Update your tests that need it.

- Jira and many tools like it keep a "history" of any "issues" you've created,
  so you can always access old versions.
- Otherwise some testers like to maintain "versioning" on their tests.
  - They'll "retire" a test that is no longer up to date, mark it with the
    versions it was accurate for, and then create a new test for the updated
    functionality.

Take note of any additional tests you may need, or bugs you find, while you
update your tests.

- This is frequently where a QA will find a LOT of bugs with a new release.
- Even things that seem simple or clear at first glance may not hold up under
  the scrutiny of reviewing/creating test cases.

## **_Good work!_**
