# Documenting Decision Rules

## Skills Practice Summary

Decision rules are all about making sure we understand how combinations of a set
of inputs lead to sets of outputs. We'll use a simple system to practice this.

### System: Message Notifications

Given that a user has received a message, a notification will be generated based
on the following statements:

- If notifications are muted at the system level, no notification will be sent.
- If "Do Not Disturb" hours are set, and the message is received during those
  hours, there will be no notification.
- If "Do Not Disturb" hours are set, and the message is received outside those
  hours, notifications will be generated.
- If the sender of the message is a "favorite" contact, "Do Not Disturb"
  settings are overridden to generate notifications.

## Step 1

1. Identify the possible actions/outcomes of the system under test.
1. Identify the conditions/inputs of the system under test.

<details  markdown="1"> <summary> Conditions/Inputs && Actions/Outputs </summary>

- Conditions/Inputs
  - System Level Notification Mute
  - Do Not Disturb Hours Set
  - Message Received During DND Period
  - Sender is a "Favorite" Contact
- Actions/Outputs
  - Notification Generated
  - No Notification Generated

</details>

## Step 2

1. Create a table like the following example table, where:
   - One axis has the Conditions/Inputs, as well as the Actions/Outputs
   - The other axis will contain the "Rules"
2. Populate the rows with the items you discovered in Step 1.

<details  markdown="1"> <summary> Empty Example Table </summary>

|                       | Rule 1 | Rule 2 | Rule 3 | etc... |
| --------------------- | ------ | ------ | ------ | ------ |
| **Conditions/Inputs** |        |        |        |        |
| condition/input 1     |        |        |        |        |
| condition/input 2     |        |        |        |        |
| **Actions/Outputs**   |        |        |        |        |
| action/output 1       |        |        |        |        |
| action/output 2       |        |        |        |        |

</details>

<details  markdown="1"> <summary> Step 2 Solution </summary>

|                        | Rule 1 | Rule 2 | Rule 3 | etc... |
| ---------------------- | ------ | ------ | ------ | ------ |
| **Conditions/Inputs**  |        |        |        |        |
| System Muted           |        |        |        |        |
| DND Hours Set          |        |        |        |        |
| Received in DND Period |        |        |        |        |
| Sender is a Favorite   |        |        |        |        |
| **Actions/Outputs**    |        |        |        |        |
| Notification Generated |        |        |        |        |

</details>

## Step 3

- Populate the columns of the table for all viable combinations of inputs.
  - _Viable_ is an important consideration; as some combinations are not
    possible; can a message be received during the "Do Not Disturb" period if
    those hours were never defined?
- You can do this in any order you want to really.

<details  markdown="1"> <summary> Step 3 Solution </summary>

|                        | Rule 1 | Rule 2 | Rule 3 | Rule 4 | Rule 5 | Rule 6 |
| ---------------------- | ------ | ------ | ------ | ------ | ------ | ------ |
| **Conditions/Inputs**  |        |        |        |        |        |        |
| System Muted           | False  | False  | False  | False  | False  | True   |
| DND Hours Set          | True   | True   | True   | True   | False  | n/a    |
| Received in DND Period | True   | False  | True   | False  | n/a    | n/a    |
| Sender is a Favorite   | True   | True   | False  | False  | n/a    | n/a    |
| **Actions/Outputs**    |        |        |        |        |        |        |
| Notification Generated | True   | True   | False  | True   | True   | False  |

</details>

## Step 4

- Write up a test that would check that the system works according to the rules
  you found.
- Consider how you would try to break each rule; a tester needs both positive
  and negative tests to be confident in their results!

<details  markdown="1"> <summary> Possible Tests </summary>

**Test 1**

- Repeat the following steps for each "rule"

1. Set test mute, dnd, message time, and message sender appropriately.
1. Send the message.
1. Verify thata notification was, or was not, generated.

**Test 2**

- Do exploratory testing were for each rule, attempt to bypass expected results.
  - For example:
    - Test right when DND hours roll over.
    - Set and delete DND hours and then try messaging inside or outside them.
    - Try various combos of times/senders to see if a notification is generated
      regardless of system mute.

</details>

## Stretch

Find another system to practice with:

- A late fee generation system
- A video game achievement system
- etc.

## **_Good work!_**
