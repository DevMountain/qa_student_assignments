# Update Tests For Acceptance Criteria

## Skills Practice Summary

Remember, acceptance testing is testing with customers in mind, what they need
in your application for it to be "acceptable".

## Setup

- Have the application requirements handy:
  [Employee Manager v1.1 Requirements](https://devmountain-qa.github.io/employee-manager/1.1_README.html).
- Skim the email from the customer in [Skills Practice 1.03.1](./sp1.03.1.md).
- You can use your test from [Skills Practice 1.02.2](../1.02/sp1.02.2.md), or
  the solution test cases provided there.

## Step 1

Try and determine "acceptance criteria" - although they are usually provided to
us, it's good practice to look at an app (or plan for one) and anticipate what
the user will want.

You can compare your answers with the list of acceptance criteria compiled below
(these include a few points from the customer email, which may or may not be
applied by the product owner).

<details> <summary> Acceptance Criteria </summary>

- As a user I can view the name, phone number, title, email address, and
  employee ID of employees in the contact manager.
- As a user I can edit the name, phone number, title, and/or email address for
  employees I have authority over.
- As a user I can abandon or cancel edits; changes will only stay if I save
  them.
- As a user I can search through the contacts in the manager.
- etc.

</details>

## Step 2

In Jira, find your test case(s) from
[Skills Practice 1.02.2](../1.02/sp1.02.2.md), or:

- \*Solution\* Swapping Records Mid-Edit
- \*Solution\* Edit Name

Review the tests as they currently stand, and your acceptance criteria. Which
criteria are covered? Which aren't?

<details> <summary> For example... </summary>

By our solution tests and example acceptance criteria alone:

- The "view" acceptance criteria is covered
- The "edit" acceptance criteria is covered, except that we have nothing
  checking user authorization, which is ok, considering that we have nothing in
  the app for that right now.
  - We still need to be aware of that.
- "As a user I can abandon or cancel edits, changes will only stay if I save..."
  - We test swapping records
  - We need to test:
    - Cancelling
    - Saving, navigating away, then back
- The "search" acceptance criteria is not covered, but like the "edit"
  acceptance criteria, the app doesn't have that functionality just yet, we only
  need to know we'll need to look at it in the future.

</details>

## Stretch

- Go through the process and update your tests to match the acceptance criteria
  YOU determined.
- Consider whether you've made any risky changes -
  - Did you define acceptance criteria your product owner might not sign off on?
  - Are you testing criteria the app doesn't yet support? If so, you need to be
    ok with either NOT running the test, or ignoring that it fails every time
    until you've developed that part of the application.

## **_Good work!_**
