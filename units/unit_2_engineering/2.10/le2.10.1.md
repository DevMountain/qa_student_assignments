# JMeter Tests

#### Target Time +/- 120 minutes

## Summary

JMeter is a powerful tool to hit sites hard with traffic. On a decent machine,
you can usually get a couple of hundred requests out pretty quickly, assuming
the responses aren't too big.

- You can check response content and size, etc.

## Step 1

1. Create a new JMeter test plan for TYJA!
1. You can go ahead and create a config element and thread group.
   1. Start small on the thread group.

## Step 2

Using a request you've copied from the network tab (you should already have one
in Postman), add a Sampler: HTTP Request.

## Step 3

Make an assertion on something unique to the response to your request!

## Step 4

Add a listener to watch your assertion(s).

## Step 5

1. Slowly add threads until your computer seems to start to struggle to keep up.
1. Then add a loop or two.

## Step 6

Consider, are any problems thus far your computer's fault? Are the issues in the
API itself?

## Step 7

Add more assertions to check!

## Submission

Save and submit your JMeter testing as a `.jmx` file in Canvas.

## Solution

Check out the `2.10` branch in `qa_playground` for `TYJA_Example.jmx` an example
solution!

## Stretch

Can you bring down TYJA?
