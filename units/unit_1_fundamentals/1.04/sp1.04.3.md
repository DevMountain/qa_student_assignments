# Leverage State Transition Testing

## Skills Practice Summary

What states are there in Employee Manager that we need to watch?

## Setup

- Have the application open:
  <a target="\_blank" href="https://devmountain-qa.github.io/employee-manager/1.1_Version/index.html">Employee
  Manager v1.1</a>
- Grab your notes from our earlier examples of state transition diagrams.

## Step 1

Create a state transition diagram showing the user's flow through the
application.

Remember:

- The boxes are "states"
- The connecting lines are "transitions"

**Example**:
<img src="https://devmountain.github.io/qa_student_assignments/assets/stateTransitionExample.png" />

- In this example, a guest or account holder views a special sale where they can
  wish for sale items, and then share those wishes; but a guest user will need
  to sign up for an account to share.

<details  markdown="1"> <summary> Possible Solution </summary>

Your diagram might look different, and that's ok!

<img src="https://devmountain.github.io/qa_student_assignments/assets/emStartingST.png" />

</details>

## Step 2

Review your diagram, and compare it to testing you have in place.

For each state/transition:

- Is it covered by one or more tests? Do you think you need more test coverage?
  - Color code your diagram for
    - Sufficient coverage
    - Needs additional coverage
- Are there known bugs for that item?
  - Mark it with red to indicate known issues
- Is that part of the app still under development?
  - Color code it a different way

<details  markdown="1"> <summary> Possible Solution </summary>

As before, yours might look different, but:

- Red = known bugs
- Blue = needs coverage
- Green = good

<img src="https://devmountain.github.io/qa_student_assignments/assets/emColoredST.png" />

</details>

## Step 4

Practice reporting using your diagram:

- Could write up an email explaining the status of the different parts of your
  feature or application
- Practice reporting to a classmate, friend, or yourself in your mirror/camera

## Stretch

Create state transition diagrams for key flows in your favorite mobile app, or
even a video game.

- Try explaining it to someone else, see if you're missing anything

## **_Good work!_**
