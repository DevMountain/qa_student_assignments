# Group Capstone - Polish

<table>
<tr>
<th> Table of Contents </th>
<th> Prior Content </th>
</tr>
<tr>
<td markdown="1">

- [Summary](#summary)
- [Step 1 - Code Cleanup](#step-1---code-cleanup)
- [Step 2 - README.md](#step-2---readmemd)
- [Submission](#submission)
- [Up Next](#up-next)

</td>
<td markdown="1">

- <a href="../2.11/project2.01.html">Kickoff</a>
- <a href="../2.11/project2.02.html">Preliminary Plannng</a>
- <a href="../2.12/project2.03.html">Plan Review</a>
- <a href="../2.12/project2.04.html">Setup</a>
- <a href="../2.12/project2.05.html">First Iteration</a>
- <a href="../2.13/project2.06.html">Second Iteration</a>
- <a href="../2.14/project2.07.html">Third Iteration</a>

</td>
</tr>
</table>

---

## Summary

It's time to get the group together and clean up the code base, as well as
assess if there are any last minute changes to be made.

This will also be a great time to get your README.md together!

---

## Step 1 - Code Cleanup

1. Make sure all required changes are merged in.
   - Did you miss any required pieces from your test plan?
1. Check and make sure the tests run correctly.
   - Use more than one machine to check this - not all computers run the same
     way.
1. Fix any bugs you find in this process.
   - You can assign them out to one or two team members while the rest of the
     team keeps going.
1. Does your code make sense?
   - You don't want "spaghetti code" that's hard to follow.
   - If needed, clean up the file structure, split things out into different
     files/modules, or merge things back together as needed.
   - Whatever you change, make sure the whole thing still works.
1. Check/add comments.
   - While you don't need a novel explaining each function, make sure you have
     comments in your code that can help someone new to the project understand
     what's going on.
   - Clearly named classes/methods can make this much easier.
1. Commit, push, and merge any changes made in this process.
1. Reverify on multiple machines.

---

## Step 2 - README.md

Your project has a README file at it's base. This is the landing page for the
project in GitHub.

> **Note:** GitHub put together a
> <a href="https://guides.github.com/features/mastering-markdown/" target="\_blank">good
> guide to markdown</a> formatting, which is what the README uses.

You can use the following template if you want, or come up with your own, but
put together a doc that would help a potential hiring manager understand how you
put your project together and how to use it.

> **Please Note:**
>
> - This template is for structure ideas only. Do not use the placeholder text.
> - Avoid using references to specific issues/content in Jira, as that will not
>   be available to those who might review the project.

<details markdown="1"><summary><code>README_Template.md</code></summary>

```markdown
# My Project

- [Summary](#summary)
- [Setup](#setup)
- [Running Tests](#running-tests)
- [What Do We Test](#what-do-we-test)
- [How Do We Test](#how-do-we-test)
  - [Page Objects](#page-objects)
  - [Data Files](#data-files)

## Summary

This project was put together to test some application. It uses Jest as a test
runner, and Selenium Webdriver to hook into the browser.

## Setup

This is how to set up my project.

1. clone it!
1. `npm i`

## Running Tests

To run all the tests, use the command: `npm test`

To run a specific test, use the command: `npx jest test_name`

## What Do We Test

The functionality we test is like this...

## How Do We Test

We organized our tests using this structure...

### Page Objects

We made page objects for these pages because...

- page 1
  - More info...
- page 2
- page 3

### Data Files

Iteration is key to test some specific functionality, so we created files for...
```

</details>

---

## Submission

No submission is required here, as you will submit your project after the
retrospective.

---

## Up Next

Now that your project is just about wrapped, you'll have a retrospective where
your team will have the chance to talk about lessons learned, you can update a
few final pieces and get ready for your presentation.
