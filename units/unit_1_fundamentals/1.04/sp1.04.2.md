# Streamline down to Regression Testing

## Skills Practice Summary

Once your application is "done", or at least a good chunk has been developed,
you shouldn't spend your time testing EVERY LITTLE PIECE over and over again.
It's important to have good regression tests.

Generally, a good regression test

- Is faster to run than similar tests covering the same funcitonal area(s)
- Has a broader focus

Plan ahead -- what would a good regression test look like for employee manager,
with the current functionality?

## Setup

- Have the application requirements handy:
  [Employee Manager v1.1 Requirements](https://devmountain-qa.github.io/employee-manager/1.1_README.html).

* If you have tests for Employee Manager, have them available for review.

## Step 1

Do your best to write ONE test that incorporates the most important features of
Employee Manager, and the criteria for a "good regression test" as described
above.

If you absolutely need to have two, that's fine.

<details> <summary> For example ... </summary>

A decent regression test might read like this:

> - Select an employee.
> - Edit the employee to have invalid entries, click save, and verify the right
>   errors appear.
> - Fix the errors with a second set of edits, valid this time, and save.
> - Navigate to another employee and back, verify the edits persisted.

</details>

## Stretch

- Pick a favorite web application, and write a "regression test" you could use
  to double check your favorite feature after their next update.

## **_Good work!_**
