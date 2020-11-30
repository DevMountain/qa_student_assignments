# Interpret Comments

#### Target Time Limit: +/- 15 minutes

## Summary

Comments are an essential part of clean, maintainable code. Naming conventions
and clean patterns are other parts, but being able to read comments and
UNDERSTAND what's going on? That's huge.

## Example 1 - No Comment

Have you ever had to come back to something after you haven't touched it in
weeks? It can be tough.

Let's say you're coming back to a project that you have to maintain, and there's
nothing. Like this.

<details markdown="1"> <summary> Snippet: No Comment </summary>

```typescript
import { calculate } from "./calculate";

const CLEAR = "CLEAR";
const ENTER_NUMBER = "ENTER_NUMBER";
const EVALUATE = "EVALUATE";
const PERCENTAGE = "PERCENTAGE";
const SET_OPERATOR = "SET_OPERATOR";
const TOGGLE_NEGATIVE = "TOGGLE_NEGATIVE";

const initialState = {
  currentValue: "0",
  operator: null,
  previousValue: 0,
  needNewValue: false,
};

export default function calculator(state = initialState, action) {
  switch (action.type) {
    case ENTER_NUMBER:
      return {
        ...state,
        currentValue:
          state.currentValue === "0" || state.needNewValue
            ? action.number.toString()
            : `${state.currentValue}${action.number}`,
        needNewValue: false,
      };
    case SET_OPERATOR:
      return {
        needNewValue: true,
        currentValue: state.previousValue,
        operator: action.operator,
        previousValue: state.operator
          ? calculate(
              parseFloat(state.currentValue),
              state.previousValue,
              state.operator
            )
          : parseFloat(state.currentValue),
      };
    case PERCENTAGE:
      return {
        ...state,
        currentValue: (parseFloat(state.currentValue) / 100).toString(),
      };
    case CLEAR:
      return {
        currentValue: "0",
        operator: null,
        previousValue: 0,
      };
    case EVALUATE:
      return {
        currentValue: calculate(
          parseFloat(state.currentValue),
          state.previousValue,
          state.operator
        ).toString(),
        operator: null,
        previousValue: 0,
        needNewValue: true,
      };
    case TOGGLE_NEGATIVE:
      return {
        ...state,
        currentValue: (-parseFloat(state.currentValue)).toString(),
      };
    default:
      return state;
  }
}

export function clear() {
  return { type: CLEAR };
}

export function enterNumber(number) {
  return { number, type: ENTER_NUMBER };
}

export function evaluate() {
  return { type: EVALUATE };
}

export function percentage() {
  return { type: PERCENTAGE };
}

export function setOperator(operator) {
  return { operator, type: SET_OPERATOR };
}

export function toggleNegative() {
  return { type: TOGGLE_NEGATIVE };
}
```

</details>

Ok. Time to fix a bug! If people hit the `+/-` button before they've entered a
number, there's no negative! Go!

- Wait - is that a bug? Is it working as intended? Where do I even go to do
  this?
- We export a toggle at the end, is that it?

You can probably get to figuring this out. But no comments makes it difficult,
and you might misunderstand something, especially if the code is complex.

---

## Example 2 - Too Much Information

If you've ever found yourself distracted by getting TOO much of an answer back
on a question, you probably won't overuse comments.

<details markdown="1"> <summary> Snippet: Too Much Information </summary>

```typescript
/* we import our calculate function so that we can actually do the math.
We just track the stuff that has to do with organizing the uncalculated stuff
here. */
import { calculate } from "./calculate";

// this is for the clear button
const CLEAR = "CLEAR";
// this is for when people punch in a number
const ENTER_NUMBER = "ENTER_NUMBER";
// this is the equals button command. Why not just equals?
const EVALUATE = "EVALUATE";
// turns a value into a percentage, only not really. Just divides it by 100
const PERCENTAGE = "PERCENTAGE";
// sets what kind of math we're doing next
const SET_OPERATOR = "SET_OPERATOR";
// changes the number to be negative. Unless it's zero. Zeros can't be negative.
// can you imagine? negative nothing?
const TOGGLE_NEGATIVE = "TOGGLE_NEGATIVE";

// the initial value of the state
const initialState = {
  currentValue: "0", // when you boot up the calculator, it's at zero!
  operator: null, // when you boot up, you aren't doing math
  previousValue: 0, // and you didn't do math
  needNewValue: false, // and you can't have hit a button to make you need a new number
};

/* now the calculator's brain lives here. state lets us pass in a new state for
when the calculator is in use, but we get a default value of the initial state.
the action is nice, it has to be one of the values up above, it's basically
what happens when somebody hits a button. This handles all that stuff. */
export default function calculator(state = initialState, action) {
  switch (action.type) {
      /* switch statements can be pretty cool. They are like if statements
      but you don't have to stack them on top of each other */
    case ENTER_NUMBER:
      return {
        ...state, /* if you haven't tried one before, a spread operator is awesome! */
        // this one basically says, hey, things stay the same, unless they don't.
        // see how we set a new current value below?
        currentValue:
          state.currentValue === "0" || state.needNewValue
            ? action.number.toString()
            : `${state.currentValue}${action.number}`,
        needNewValue: false, // and if someone entered a number, then the next
        // entry doesn't have to be a new number. Duh.
      };
      //...
```

</details>

Pretty awful, huh? The comments aren't necessarily bad. And honestly, if you're
brand new to the coding business, they might seem pretty helpful! I think in
many ways, they're better than nothing. BUT, they can make it more difficult to
find the information you actually care about.

---

## Example 3 - Just Right. Well, it depends.

How much is too much? Too little? Up to you. Different people have different
styles. Different companies have different standards.

I tend to like fewer comments, but easy to read code. That said, I also like
TypeScript and JSDocs, both of which can be a pain to work with sometimes, but
give a LOT more hints about how your code should be working. More on JSDoc
later, but let's look at those comments...

<details markdown="1"> <summary> Snippet: Just Right. For me. </summary>

```typescript
import { calculate } from "./calculate";
// actual math happens in calculate

// these are the actions that can be passed into the calculator
const CLEAR = "CLEAR";
const ENTER_NUMBER = "ENTER_NUMBER";
const EVALUATE = "EVALUATE";
const PERCENTAGE = "PERCENTAGE";
const SET_OPERATOR = "SET_OPERATOR";
const TOGGLE_NEGATIVE = "TOGGLE_NEGATIVE";

// initial boot up values; only used if no buttons have been pressed
const initialState = {
  currentValue: "0",
  operator: null,
  previousValue: 0,
  needNewValue: false,
};

export default function calculator(state = initialState, action) {
  // based on the action is passed in, the calculator's 'brain' will act differently
  switch (action.type) {
    /* if a number is entered, we update the current value; 
      replacing what's displayed if the current value is 0,
      or if the last butotn press WASN'T a number,
      otherwise adding to it */
    case ENTER_NUMBER:
      return {
        ...state,
        currentValue:
          state.currentValue === "0" || state.needNewValue
            ? action.number.toString()
            : `${state.currentValue}${action.number}`,
        needNewValue: false,
      };
    /* sets whether we're multiplying/adding/dividing/subtracting if one of
      those buttons was hit; marks that we'll need a second number now */
    case SET_OPERATOR:
      return {
        needNewValue: true,
        currentValue: state.previousValue,
        operator: action.operator,
        previousValue: state.operator
          ? calculate(
              parseFloat(state.currentValue),
              state.previousValue,
              state.operator
            )
          : parseFloat(state.currentValue),
      };
    /* takes the current value and divides it by 100 */
    case PERCENTAGE:
      return {
        ...state,
        currentValue: (parseFloat(state.currentValue) / 100).toString(),
      };
    /* clears the operator and values, and sets it back to 0 */
    case CLEAR:
      return {
        currentValue: "0",
        operator: null,
        previousValue: 0,
      };
    /* Takes the previous value, current value, and operator, and sends them
      through the calculate function, displaying the new value */
    case EVALUATE:
      return {
        currentValue: calculate(
          parseFloat(state.currentValue),
          state.previousValue,
          state.operator
        ).toString(),
        operator: null,
        previousValue: 0,
        needNewValue: true,
      };
    /* Takes the current value and makes it negative */
    case TOGGLE_NEGATIVE:
      return {
        ...state,
        currentValue: (-parseFloat(state.currentValue)).toString(),
      };
    /* If it gets confused, returns the previous state, changing nothing */
    default:
      return state;
  }
}

// Frankly, not sure why it was set up this way...
// An enumerator would be cleaner, but this works to make sure only the right
// actions are used.

export function clear() {
  return { type: CLEAR };
}

export function enterNumber(number) {
  return { number, type: ENTER_NUMBER };
}

export function evaluate() {
  return { type: EVALUATE };
}

export function percentage() {
  return { type: PERCENTAGE };
}

export function setOperator(operator) {
  return { operator, type: SET_OPERATOR };
}

export function toggleNegative() {
  return { type: TOGGLE_NEGATIVE };
}
```

</details>

---

## Next Steps

Whatever makes the most sense to you; that's what you should shoot for. If you
would like more explanation in the middle of a function, or a for loop, or
something, DO IT! Especially while you're learning, too much beats too little.
Experiment. If you see someone's style and you like it, run with it!

For now though, go back to some of our previous code exercises, and add your own
comments! Try to comment two files two different ways. Add comments to your next
file on the fly as you write it!

Or even, one of my favorite, **comment first**.

- When writing up automation:
  1. Add comments for the setup
  1. Add comments for the assertions you'll make
  1. Add comments in the middle for the steps you'll take to get from setup to
     assertions
  1. THEN code.
- I miss a lot less that way.

Bottom line, get practicing!
