# Data Sets

#### Target Time Limit: +/- 60 minutes

## Summary

As you're getting more used to coding, it's important that you start thinkging
about how you can leverage your knowledge and apply it to quality assurance.

For now, you'll be looking over manual tests and considering how you could break
things down to repeated steps using data sets.

## Instructions

### Information Gathering

1. Pick any one of your projects in Jira, and select a test that would be
   repeated multiple times.
   - Like editing an employee in "Employee Manager"
   - Or adding a job in "Track Your Job Application"
1. Make sure you have, in detail, identified each of the steps you'd take for
   this test.
1. For each step, identify the data needed: _ Inputs or _ Expected results Once
   you have the steps, and all of the data you need for each step, you are ready
   to proceed.

### Data Generation

1. Create multiple sets of data (inputs and expected results) for the test you
   identified.
   - Any one set should be able to go through your steps successfully and pass
     the test, or identify a problem.
1. Attach the list of data sets to the test in Jira.

## Stretch Goal

Create a `.ts` file where you define a class to hold each data set, and build
out an array of each set. You can attach this file to the test as well.

## Submission

To submit this assignment, simply submit a link here in Canvas to the test
you've attached your data set to.

## Solution

See
[QEP-1](https://dmutah.atlassian.net/jira/software/c/projects/QEP/issues/QEP-1)
in Jira for an example.
