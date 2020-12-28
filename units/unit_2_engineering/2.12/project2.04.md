# Group Capstone - Setup

#### Target Time Limit: +/- 60 minutes

<table>
<tr>
<th> Table of Contents </th>
<th> Prior Content </th>
</tr>
<tr>
<td markdown="1">

- [Summary](#summary)
- [GitHub Repository](#github-repository)
  - [1. Add Repository](#1-add-repository)
  - [2. Set Up Project Framework](#2-set-up-project-framework)
  - [3. Set up for collaboration](#3-set-up-for-collaboration)
  - [4. Check Setup](#4-check-setup)
- [Next Up](#next-up)

</td>
<td markdown="1">

- <a href="../2.11/project2.01.html">Kickoff</a>
- <a href="../2.11/project2.02.html">Preliminary Plannng</a>
- <a href="../2.12/project2.03.html">Plan Review</a>

</td>
</tr>
</table>

---

## Summary

Now is the time to get together with your team and make sure you are all working
off of the same code base.

---

## GitHub Repository

Pick one person - it doesn't matter who - to set up your shared repository. They
will follow these instructions.

### 1. Add Repository

1. Log in to [github.com](https://www.github.com)
1. Click the "+" icon in the menu and select "New Repository"
1. Make sure that you (the creator) are the "Owner" of the repository
1. Give the repository a name appropriate for the app you are testing.
1. The rest of the defaults can be left as they are: Click "Create repository."

### 2. Set Up Project Framework

1. Clone the repository to your local machine.
1. Add the following files; you should be able to copy them in from other
   projects, but here are some great default values:

   - <details markdown="1"><summary><code>.gitignore</code></summary>

     ```
     node_modules
     ```

        </details>

   - <details markdown="1"><summary><code>jest.config.js</code></summary>

     ```javascript
     module.exports = {
       preset: "ts-jest",
       testEnvironment: "node",
     };
     ```

       </details>

   - <details markdown="1"><summary><code>package.json</code></summary>

     ```json
     {
       "name": "someProject",
       "version": "1.0.0",
       "description": "",
       "main": "",
       "scripts": {
         "test": "jest"
       },
       "keywords": [],
       "author": "",
       "license": "ISC",
       "dependencies": {
         "@types/jest": "^26.0.15",
         "@types/selenium-webdriver": "^4.0.10",
         "chromedriver": "^87.0.0",
         "geckodriver": "^1.21.0",
         "jest": "^26.6.3",
         "selenium-webdriver": "^4.0.0-alpha.7",
         "ts-jest": "^26.4.4",
         "ts-node": "^9.0.0",
         "typescript": "^4.0.5",
         "@types/axios": "^0.14.0",
         "axios": "^0.21.0"
       }
     }
     ```

        </details>
       
        * Edit this to have YOUR project name.

   - <details markdown="1"><summary><code>README.md</code></summary>

     ```md
     # someProject

     This project showcases our collaborative automation efforts to test
     someSite.

     Authors:

     - someone
     - another
     - etc.

     To execute these tests:

     1. Install dependencies: `npm i`
     1. Execute the tests: `npm test`
     ```

       </details>

     - Edit this to have YOUR project details (name, authors, app to test,
       etc.).
     - Feel free to add more detail here.

   - <details markdown="1"><summary><code>tsconfig.json</code></summary>

     ```json
     {
       "compilerOptions": {
         "resolveJsonModule": true
       }
     }
     ```

       </details>

1. Set up the file structure for your tests; you can copy another structure, or
   outline it soething like this:
   ```
   |- | __tests__
   |  |- | pageObjects
   |  |  |- placeholder.ts
   |  |- | data
   |     |- placeholder.ts
   |- .gitignore
   |- jest.config.js
   |- package.json
   |- README.md
   |- tsconfig.json
   ```
   - In this example, `__tests__`, `pageObjects` and `data` are all folders. You
     might have a few more default files, like a README or package-lock, but
     this should cover the bases.
   - Having some sort of placeholder is important, as git will not track empty
     folders.
1. Add, commit, and push up your changes.

### 3. Set up for collaboration

Back up on GitHub...

1. Open your repository's "Settings", which is one of the main repository tabs.
1. In the menu on the left, pick "Manage Access"
1. You should see a section called "Manage Access" that warns you that you have
   not invited anyone. Click "Invite Teams or People".
1. In the modal that pops up, input your group mate's usernames or emails.

Once they accept your invitations, they will be able to push up to this
repository as well.

### 4. Check Setup

Have all students clone down the repository and make sure that all the files are
present, and everything looks great!

---

## Next Up

Now it's time to actually start working.
