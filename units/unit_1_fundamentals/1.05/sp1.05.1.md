# Patch Gaps in Coverage

## Skills Practice Summary

Having experience patching holes in your testing "net" is very important.

- You need to be able to spot those gaps first.
- Once you know they exist, you need to be able to figure out an effective way
  to close them.

## Setup

- Have your workflow for the prior version of Employee Manager, or you can use
  the solution mentioned in
  <a target="\_blank" href=".https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/1.04/sp1.04.3.html">Skills
  Practice 1.04.3</a>.
- Open the requirements for
  <a target="\_blank" href="https://devmountain-qa.github.io/employee-manager/1.2_README.html">Employee
  Manager v1.2</a>.

## Step 1

Review the change log for version 1.2.

- What has changes that isn't included in your existing testing?
- Review your state transition diagram - remember, it can serve to track
  coverage.
- Update your diagram, including marking off any areas that do not have
  sufficient test coverage.

<details  markdown="1"> <summary> Possible solution... </summary>

![Updated employee manager state transition
diagram<img src=".https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/.https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/.https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/assets/needAsset.png" />

</details>

## Step 2

It's time to add tests for any areas completely missing coverage.

- As you do, you may think of additional areas that need testing, or situations
  that need exploring. Be sure to take note.

**Note:** Do not worry about updating existing test cases for this practice
exercise, as that will be covered in
<a target="\_blank" href="https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/sp1.05.2.html">Skills
Practice 1.05.2</a>.

## Step 3

If you were limited on time, how would you know which tests needed updating or
executing the soonest?

- Review the areas that need new tests or updates to existing tests
- Perform Risk Analysis, and estimate the Level of Risk for each.
  - Likelihood: An estimate of how likely a problem is to occur (either a
    percentage, or a 1-5 scale, etc.)
  - Cost: An estimate of the cost (could be in \$\$, time, etc)
  - Level of Risk = Likelihood \* Cost
- Pick the three areas you'd definitely cover, and the one you would let slide
  if you needed.

## **_Good work!_**
