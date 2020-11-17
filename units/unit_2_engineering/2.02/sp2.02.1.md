# Effective Function Design

We're going to give you a pattern to follow to make a function, and you can make
your own!

## Setup

It'd be easiest to just use your `qa_playground` project, since that exists for
practice, but NOT submission, so you don't need to worry about adding "perfect"
code here. It's all for messing around!

- You can create a new folder in your `src` folder named `practice`
- In here, make a new file called `creatingFunctions.ts`

## Step 1

Declare a new function. _ Name it `fancyPrint` _ It should have two string
parameters. _ `firstString` _ `secondString` \* It should return a string. The
pattern is as follows for typescript:

```typescript
function funcName(parameter1: type1, parameter2: type2): returnType {
  //code goes here
}
```

<details markdown="1"><summary>Solution: <code>creatingFunctions.ts</code></summary>

```typescript
function fancyPrint(firstString: string, secondString: string): string {
  //code goes here
}
```

</details>
<br/>

## Step 2

Your function should build and return a new string based on the two strings. It
should be formatted like this:

1. First, `string1`
1. Then a bunch of asterisks
1. A new line
1. A bunch more asterisks
1. Then `string2`

Something like:

```
********value of string 1
value of string 2********
```

### You'll need

- `npx ts-node src/creatingFunctions.ts`
  - this command in your terminal will run the creatingFunctions file if you
    coded it as described.
- `return`
  - Whatever comes after this (the variable storing your string, or even the
    logic combining it) is what gets returned.
- `+`
  - You can add strings together with this.
  - Or, you could use string interpolation with
    - <code>`</code> backsticks starting/ending the string
    - `${myVar}` or `${2+2}` which evaluates whatever is in the {}s and drops it
      into the string, in this case the value of myVar, or the number 4.
  ```typescript
  `We have value 1: "${val1}" that will be quoted there. "${val2}" here.` +
    `\n\tSincerely,\n\t${authorName}`;
  ```
- `\n`
  - Drop this into a string to add a new line anywhere.
- `\t`
  - If you want to get fancy, this is the "tab" character.

## Examples

<details markdown="1"><summary>String concatenation example, no solution</summary>

<br />

Look over this code for `+` concatenation and "string interpolation"

```typescript
var stringA = "Hello";
var stringB = "world";

console.log(stringA + " " + stringB);
console.log(`${stringA} ${stringB}!`);
```

This will print:

```
Hello world
Hello world!
```

</details>

<br />

<details markdown="1"><summary>Function return example, no solution</summary>

<br />

We'll have a function that returns a string that we print out in this code.

```typescript
function returnMyName(name: string): string {
  var myString = "**********\n\t\t" + name + "\n\t\t\t**********";
  return myString;
  //this IS the same as the following commented line, but some think
  //it is easier to read:
  //
  // return "**********\n\t\t" + name + "\n\t\t\t**********"
}

console.log(returnMyName("Bob"));
```

Which will print:

```
**********
                Bob
                        **********
```

</details>

<br />

## Solution

The solutions for today's skills practices will be in the `2.02` branch of the
`qa_playgrounds` repository.

<details markdown="1"><summary><strong>Solution: <code>creatingFunctions.ts</code></strong></summary>

### Code

```typescript
function fancyPrint(firstString: string, secondString: string): string {
  return `${firstString}**********\n**********${secondString}`;
}

console.log(fancyPrint("foo", "bar"));
```

### Output

This would print:

```
foo**********
**********bar
```

</details>
