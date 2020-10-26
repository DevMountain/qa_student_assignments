# Equivalence Partitioning and Boundary Value Analysis

## Skills Practice Summary

Sometimes it gets easy to fall into a rut with our testing. Knowing multiple
testing techniques can help us to adapt to different needs, and just mix it up a
little bit.

Equivalence Partitioning and Boundary Value Analysis are simple to apply, and
can help to provide us specific things to test in a broad system, without
dropping random inputs in.

## Setup

- Open
  [Employee Manager v1.2](https://devmountain-qa.github.io/employee-manager/1.2_Version/index.html)
- It can be helpful to have your tests for EM v1.2 available.

## Step 1

We'll start with Equivalence Partitioning, since Boundary Value Analysis sort of
builds off of it.

1. Pick an input field, and identify the input partitions for that field.
   - **Remember** each partition is a range of inputs that results in the same
     output.
   - It's often easiest to identify a partition by its outputs, so what are the
     "outputs" for that field?
1. Each "partition" should be tested at least once. Create one or more tests to
   cover the partitions you've determined.

<details  markdown="1"> <summary> Example partitions for a field... </summary>

If we were to consider the name field, we have the following possible outputs,
and their corresponding inputs:

| Output                                                                  | Input                         |
| ----------------------------------------------------------------------- | ----------------------------- |
| Successful save                                                         | Between 1 and 30 characters   |
| Error message: The name field must be between 1 and 30 characters long. | 0, or more than 30 characters |

You could argue that we have 3 partitions for inputs, even though we only have
two outputs.

| Input           | Output          |
| --------------- | --------------- |
| 0 characters    | Error message   |
| 1-30 characters | Successful save |
| 31+ characters  | Error message   |

</details>

<details  markdown="1"> <summary> Example tests for those partitions... </summary>

**Test 1**

1. Select an employee
1. Edit the name field to be empty
1. Attempt to save
1. Make sure an error message appears, "The name field must be between 1 and 30
   characters long." and that the edit does not save

**Test 2**

1. Slect an employee
1. Edit their name to "John Smith"
1. Attempt to save
1. The edit should save successfully

</details>

## Step 2

Boundary Value Analysis is a logical extension of Equivalence Partitioning.
Where do our partitions meet? We test on either side of that boundary.

- In the United States you generally have to file your taxes (or file for an
  extension) by April 15.
  - The boundary between "on time" and "late" is as the 15th ticks over to the
    16th at midnight.
  - We would test this boundary by checking 4/15 11:59pm, and 4/16 12:00am.
  - In practice, the times may vary (closing time on the 15th, opening time the
    16th etc) but that is the basic idea.

Bugs are most likely to occur where partitions are adjacent as a developer
forgets or flips > or < signs, or other similar errors occur.

1. Using the same field you uncovered partitions for, identify boundary values
   for these partitions.
1. Update your test(s) from **Step 1** to test the boundary values you
   discovered in this exercise.

<details  markdown="1"> <summary> Example boundary vals for a field... </summary>

Considering again the name field... Looking purely at the ranges of the inputs,
we have the following partiions...

0 characters : 1-30 characters : 31+ characters

Our boundary values would then be:

- 0 characters
- 1 character
- 30 characters
- 31 characters

These would be our bare minimum values to test against this set of partitions.

</details>

<details  markdown="1"> <summary> Example tests for those boundary values... </summary>

**Test 1**

1. Select an employee
1. Edit the name field to be empty
1. Attempt to save
1. Make sure an error message appears, "The name field must be between 1 and 30
   characters long." and that the edit does not save

**Test 2**

1. Slect an employee
1. Edit their name to "J"
1. Attempt to save
1. The edit should save successfully

**Test 3**

1. Slect an employee
1. Edit their name to "John Smith 1234567890123456789"
1. Attempt to save
1. The edit should save successfully

**Test 4**

1. Slect an employee
1. Edit their name to "John Smith 12345678901234567890"
1. Attempt to save
1. Make sure an error message appears, "The name field must be between 1 and 30
   characters long." and that the edit does not save

</details>

## Stretch

Identify these same partitions and boundary values in a more complicated piece
of software.

- Note, you will have to narrow your focus, often to a single PART of a piece of
  functionality instead of the whole, as we did here with one field instead of
  all fields.

## **_Good work!_**
