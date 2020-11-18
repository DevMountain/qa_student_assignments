# Test Driven Development

Executing test driven development is pretty simple. Tests are written before the
code they're testing.

- Unit Tests
- UI Automation
- Manual Tests

Technically, having any of these types of tests ahead of time for the developers
to base their code on constitutes "Test Driven Development."

We'll be unit testing.

## Setup

Use `qa_playground` for a pre-setup testing folder.

- Create a new file in your `__tests__` folder called `tdd.test.ts` (TDD for
  test driven development)

## Step 1

Review the requirements below.

> The function you're creating tests for will be `checkIfPalindrome(string)`. It
> will return true if the string passed in is a palindrome, or false otherwise.
>
> - Remember, a palindrome is the same word forwards or backwards.
>   - tacocat
>   - racecar
>   - etc.

Determine your acceptance criteria for this function.

## Step 2

Sketch out testing that would verify such a function.

> Step 1 Step 2 Step 3 etc.

## Step 3

Write up unit tests that would check this. Use the placeholder below for
`checkIfPalindrome()`

```typescript
function palindromeChecker(word: string): boolean {
  return true;
}
```

Here is example test code if you need it.

```typescript
describe("plaindromeChecker", () => {
  it("", () => {});
  it("", () => {});
});
```

## Step 4

You can check your answer by copying the following function and pasting it over
the placeholder you had.

- Note: This function should work, and so your tests should pass.

```typescript
function palindromeChecker(word: string): boolean {
  if (!word) return false;
  const reversedWord: string = word.trim().split("").reverse().join("");
  return reversedWord.toLowerCase() == word.trim().toLowerCase();
}
```

Run your test with the command `npx jest tdd` - once you have more tests you'll
probably need a more specific command, like
`npx jest src/__tests__/ttd.test.ts`, so that Jest can tell your tests apart.

## Solution

The solutions for today's skills practices will be in the `2.02` branch of the
`qa_playgrounds` repository.
