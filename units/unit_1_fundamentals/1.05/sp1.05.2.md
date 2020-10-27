# Add Traceability

## Skills Practice Summary

Being able to find your way from a bug to a test is useful.

- From a test to documentation equally so.
- From a bug to the requirements for that piece of software? Awesome for your
  developers.

Traceability makes it easier for us to see the big picture, and for anyone to be
able to find answers more readily.

## Setup

- Pull up a bug _you_ reported in Jira.

## Step 1

Look at your bug report in Jira.

- Does it look good?
- Does it have the level of detail it needs?

Your bug report would do well to be linked to a test that checks it out.

Link them together, marking that your test "Tests" the bug report.

<!-- - See this <a target="_blank" href="https://devmountain.github.io/qa_student_assignments/units/unit_1_fundamentals/1.05/">tutorial</a> if you need help figuring out how to
  link Jira issues together. -->

This will make life WAY easier for the QA that gets the job to do confirmation
testing for the bug fix, and easier for the developer who now has an idea how to
make sure they fixed the bug adequately!

## Step 2

Link your tests to their corresponding test plans.

Now you can see all your tests FROM the test plan, which makes it eaiser to
track coverage, know what needs updating, etc.

## Step 3

Make sure that AT MINIMUM your test plan has a link to the requirements.

- If you like broad test cases, it's a good idea to link your requirements there
  too!

## Step 4

Consider how much time you've spent adding traceability to your issues.

Consider how long it would take to find all the appropriate test cases if yoyu
have 1500 tests cases?

Further, consider that some software companies have THOUSANDS of test cases
alone; not to mention bug reports, test plans, tasks for new features, etc.

It can be hard to keep track of everything; YES, adding traceability can be time
consuming, but generally offers a massive productivity bump in the long run. It
is _more_ than possible to outright lose your tests; not likely to happen though
if you link your stuff right!

## Stretch

For any of your lab exercises, update the tasks you've tested with links to
corresponding test cases, links to bugs found reviewing them, etc.

## **_Good work!_**
