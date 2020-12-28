# Group Capstone - First Iteration

#### Target Time Limit: +/- 60 minutes

<table>
<tr>
<th> Table of Contents </th>
<th> Prior Content </th>
</tr>
<tr>
<td markdown="1">

- [Summary](#summary)
- [1. Check for Updates](#1-check-for-updates)
- [2. Start a Task](#2-start-a-task)
- [3. Create a New Branch](#3-create-a-new-branch)
- [4. Code Your Changes](#4-code-your-changes)
- [5. Commit](#5-commit)
- [6. Check For Updates: Merge & Commit if needed](#6-check-for-updates-merge--commit-if-needed)
- [7. Push and Create a Pull Request](#7-push-and-create-a-pull-request)
- [8. Have Your Change Reviewed](#8-have-your-change-reviewed)
- [Iterate!](#iterate)
- [Up Next](#up-next)

</td>
<td markdown="1">

- <a href="../2.11/project2.01.html">Kickoff</a>
- <a href="../2.11/project2.02.html">Preliminary Plannng</a>
- <a href="../2.12/project2.03.html">Plan Review</a>
- <a href="../2.12/project2.04.html">Setup</a>

</td>
</tr>
</table>

---

## Summary

This is where the rubber hits the road, and you can start automating. Generally
your work will flow like this:

1. Check for updates
1. Start a task
1. Create a new branch
1. Code your changes
1. Commit
1. Check for updates, merge and commit if needed
1. Push and create a pull request
1. Have your change reviewed

This seems like a lot, but really shouldn't be too crazy.

> Note: We'll use `QE-12` as an example task number/branch name througout this
> document.
>
> Make sure to use your OWN numbers/branch names when you go through this
> process.

---

## 1. Check for Updates

You should ALWAYS make sure you're coding against up to date changes. It's
frustrating to code up a new test for a few hours, only to realize that someone
updated the page object and you need to go back and fix it.

There is really one command that will check and see if there are any updates you
don't have locally.

- `git fetch`
  - This will track any remote changes/new branches compared to your local copy
    of the repository.

To pull down updates to `master` (or `main`, depending on how youset up your
repository) you `pull`.

- `git checkout master`
  - First, make sure you're on the `master` or `main` branch.
- `git pull`
  - This will update your branch with any of those remote updates.

---

## 2. Start a Task

This is a good practice as it makes sure you're working on important things, and
that your teammates know what everyone is up to.

1. Look in Jira for the next task assigned to you.
   1. Pick the next task you can do and assign it to yourself if necessary.
1. Move this task into "in progress"

---

## 3. Create a New Branch

It's helpful to keep your code cleaner by using branches. You can name them a
number of different ways, but the issue number or summary/title are often most
useful.

There are two ways to create a branch and check it out. Let's say I'm adding a
branch for `QE-12`.

1. The original method: `git branch QE-12` `git checkout QE-12`
1. A slightly faster way `git checkout -b QE-12`

This will create the branch locally, and changes you're making now will be
applied to this new branch.

- This keeps your master branch clean and free from potentially risky changes.

---

## 4. Code Your Changes

Go ahead and add any files you need to, make any changes you need to, to
accomplish the task.

If you ever need to pull down updates from another task to finish yours, just
follow the next couple of steps and come back to finish your changes.

---

## 5. Commit

This should be pretty standard. Add and commit your changes. `git add -A`
`git commit -m 'finished work for QE-12'`

---

## 6. Check For Updates: Merge & Commit if needed

1. Fetch updates again to make sure you're comparing the right stuff.
   - `git fetch`
1. Next, pull down the remote master branch.
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

Now it is time to push your changes up to your shared repo and create a pull
request.

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
1. \*\* **DO NOT MERGE** \*\*
1. Assign teammates as code reviewers!
   - In the right hand menu, hit the cogwheel by reviewers to add reviewers to
     your pull request".
   - GitHub has an easy tutorial on using this functionality
     [here](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/requesting-a-pull-request-review).
     - `https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/requesting-a-pull-request-review`

---

## 8. Have Your Change Reviewed

This is an important phase; you will probably be asked to do code reviews too.

1. Ask one or two teammates to review your pull request. If needed, add them as
   reviewers.
1. Your peers can mark the change approved, or comment with requested changes.
   - If changes are needed:
     1. Make the changes to the branch your pull request was created for.
     1. Commit and push them back up.
1. Once approved, merge your pull request!

Make sure that any of your teammates that might need your changes know, but
otherwise, your code is now in `master`!

---

## Iterate!

You'll be going through this process repeatedly. During/between tasks you can

- Communicate with your team about how automation is going
- Adjust priorities as needed, if agreed upon

When you know where your focus is needed, pick up your next task and start this
process over!

---

## Up Next

Next class period, you'll have a standup with your team and carry on from there
with your next iteration!
