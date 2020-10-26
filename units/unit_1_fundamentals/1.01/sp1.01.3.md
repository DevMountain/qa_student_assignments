# Exploratory Testing

## Skills Practice Summary

With the notes that you have on what should be tested
(<a target="_blank" href="./sp1.01.2.html">Skills Practice 1.01.2</a>), and a
couple of examples of what has been tested
(<a target="_blank" href="./sp1.01.1.html">Skills Practice 1.01.1</a>), it's
time to do some exploratory testing.

## Setup

- Open the
  <a target="_blank" href="https://devmountain-qa.github.io/employee-manager/1.0_README.html">Employee
  Manager v1.0 Documentation</a>
- Have your notes from <a target="_blank" href="./sp1.01.2.html">Skills Practice
  1.01.2</a> handy
- Open
  <a target="_blank" href="https://devmountain-qa.github.io/employee-manager/1.0_Version/index.html">Employee
  Manager v1.0</a>

## Step 1

Using your notes, spend 15 minutes or so clicking around , testing where you
think you're the most likely to find problems.

Take notes!

## Step 2

Spend a few minutes formatting your notes on additional questions or problems
found so that you can share them with a developer or the product owner. This is,
after all, where you want to your exploratory testing to lead:

- Answering questions
- Getting problems resolved

## Solution

<details> <summary> Some problems and questions you may run across... </summary>

{% highlight markdown %}

### Bugs

- ZERO field validation. There should probably be at least some validation not
  allowing letters into phone numbers, a minimum number of characters in
  name/title, etc.
- Not _all_ IDs in the test data are positive. That could lead to some
  inconsistencies/problems in testing.
- Navigating away from unsaved changes doesn't cancel the changes.

### Questions

Most of your questions should be about formatting and user experience.

- Should there be a way to cancel out of "editing" a contact, and being in a
  "view only" mode?

Things like that.

{% endhighlight %}

</details>

## **_Good work!_**
