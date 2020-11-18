# Decisions in Tests - Conditional code

You need to understand how code decisions work. We'll cover a few variations of
`if` and `if/else` statements, and a `switch`.

## Setup

Create a new file in your `qa_playground/src` folder.

- `decisionStatements.ts`

In all your decisions, if a block SHOULD run, add

```typescript
console.log("Check 1");
```

- Increment it "Check 2", "Check 3", etc.

If the block should NOT run

```typescript
console.log("This should not print");
```

Execute your code with the command `npx ts-node src/decisionStatements.ts` and
check that you have the right number of "Check"s and no "This should not print"s
in the console.

## If

A simple if statement is written

```typescript
if (statement) {
  // action goes here, executed if the statement is true.
}
```

- Create one that will pass, and one that will fail.

## If/Else

An `if/else` is written

```typescript
if (statementA) {
  // this block executes if statementA is true
} else {
  // this block executes if statementA is false
}
```

You can also have an `else if`

```typescript
if (statementA) {
  // this block executes if statementA is true
} else if (statementB) {
  // this block executes if statementA is false
  // AND statementB is true
} else if (statementC) {
  // this block executes if statementA is false
  // AND statementB is false
  // AND statementC is true
}
```

Create each of the following:

- an `if/else`
- an `if` and `else if`
- another with a chain of `else if`s

## Switch

Switch statements take the input, go through and compare cases.

```typescript
switch (someVariable) {
  case "match1":
    // action1
    break;
  case "match2":
  // action2
  default:
  //default action
}
```

If a case matches the value of the variable, the following code will execute,
until a break is reached.

- The above example is written so that if `someVariable` matches "match2",
  `// action2` and `// default action` will both execute.

Create a switch statement, and pass in a value so that ONLY the case you want
executes.

## Stretch

Do these exercises using comparison and logic operators. | | | | | | --- | --- |
--- | --- | | `==` | `===` | `!=` | `!==` | | `<` | `<=`| `>` | `>=` | | `&&` |
`||` | `()` | `(a || b) && c` |

## Solution

The solutions for today's skills practices will be in the `2.02` branch of the
`qa_playgrounds` repository.
