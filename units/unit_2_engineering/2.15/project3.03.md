# Solo Capstone - First Iteration

<table>
<tr>
<th> Table of Contents </th>
<th> Prior Content </th>
</tr>
<tr>
<td markdown="1">

- [Summary](#summary)
- [1. Create your repository](#1-create-your-repository)
- [2. Grab a Task](#2-grab-a-task)
- [3. Create a New Branch](#3-create-a-new-branch)
- [4. Code Your Changes](#4-code-your-changes)
- [5. Commit](#5-commit)
- [6. Check For Updates: Merge & Commit if needed](#6-check-for-updates-merge--commit-if-needed)
- [7. Push and Create a Pull Request](#7-push-and-create-a-pull-request)
- [Iterate!](#iterate)
- [Submission](#submission)
- [Up Next](#up-next)

</td>
<td markdown="1">

- <a target="\_blank" href="../2.15/project3.01.html">Kickoff</a>
- <a target="\_blank" href="../2.15/project3.02.html">Planning</a>

</td>
</tr>
</table>

## Summary

Now that you have a good idea on what you're setting out to accomplish, it's
time to get started on the work itself!

This process should go almost exactly the same way as it did for your Group
Project, except that you'll be flying solo.

1. Create your repository
1. Grab a task
1. Create a new branch
1. Code your changes
1. Commit
1. Check for updates, merge and commit if needed
1. Push and create a pull request
1. Merge your pull request

This seems like a lot, but really shouldn't be too crazy.

> Note: We'll use `QE-12` as an example task number/branch name througout this
> document.
>
> Make sure to use your OWN numbers/branch names when you go through this
> process.

---

## 1. Create your repository

For this task, you can follow exactly the same setup steps as you did in the
group capstone.

- <a target="\_blank" href="../2.12/project2.04.html">Group Capstone Setup</a>

---

## 2. Grab a Task

Find your next highest priority task. This is a good time to consider if you
might need to update any prioritization as well.

If you're using Jira, make sure to move your task to "In Progress".

---

## 3. Create a New Branch

It's helpful to keep your code cleaner by using branches, even working alone.
You can name them a number of different ways, but the issue number or
summary/title are often most useful.

There are two ways to create a branch and check it out. Let's say I'm adding a
branch for `QE-12`.

1. The original method: `git branch QE-12` `git checkout QE-12`
1. A slightly faster way `git checkout -b QE-12`

This will create the branch locally, and changes you're making now will be
applied to this new branch.

- This keeps your master branch clean and free from potentially risky changes.
- If you do mess something up, you don't have to start over!

---

## 4. Code Your Changes

Go ahead and add any files you need to, make any changes you need to, to
accomplish the task.

---

## 5. Commit

This should be pretty standard. Add and commit your changes. `git add -A`
`git commit -m 'finished work for QE-12'`

---

## 6. Check For Updates: Merge & Commit if needed

1. Fetch updates again to make sure you're comparing the right stuff.
   - `git fetch`
1. Next, pull down the remote master branch. Yes, you should be the only one
   working on it, but sometimes your local branches might have been created out
   of order.
   1. You can merge it directly into the branch you're working on:
      - `git pull origin master`
      - This command tells git to pull the remote master branch into your
        current branch.
   1. You can also swap to master, pull, swap back to your new branch, then
      merge.
      - `git checkout master`
      - `git pull`
      - `git checkout QE-12`
      - `git merge`
   - Both of these examples will accomplish our task.
   - > Already up to date.
     - If this message appears you don't need to commit or fix merge conflicts.
     - Otherwise:
       1. Address the changes
       1. Check/fix your tests
       1. Add/commit once again

---

## 7. Push and Create a Pull Request

First, make sure your local branch for your changes is

- Up to date
- Working

Now it is time to push your changes up to your repo and create a pull request.

1. Push up your commit(s).
   - `git push origin QE-12`
   - This will push your code up from Git to GitHub.
   - You _may_ need to put in your username/password for this to work.
1. Check GitHub
   - Your branch should be visible in your shared repository now!
1. Create a pull request
   1. From your new branch, click the "Pull request" button at the top, where it
      says "This branch is _x_ commit(s) ahead of master."
   1. Add any needed comments about your pull request.
   1. As you do, look for the message "Able to merge"
      - If there are conflicts present, don't create a pull request yet. Pull
        the changes back down and fix them locally.
   1. Click the button "Create Pull Request" once you have comments and know
      that it can merge automatically.
1. Look things over:
   1. Are you missing files?
   1. Can you think of any problems?
1. Now, merge your changes.

---

## Iterate!

You'll be going through this process repeatedly. During/between tasks you can

- Communicate with your team about how automation is going
- Adjust priorities as needed, if agreed upon

When you know where your focus is needed, pick up your next task and start this
process over!

---

## Submission

Using Canvas, submit a link to at least one of your pull requests.

---

## Up Next

You'll be reviewing your work in groups, looking over one another's projects for
ideas and suggestions.
