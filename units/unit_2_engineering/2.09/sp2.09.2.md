# Test API Requests

#### Target Time +/- 30 minutes

## Summary

You'll add some requests in Postman with tests against our basic Employee
Manager endpoints.

## Setup

If you do not already have one, create a collection for "Employee Manager", with
the following queries:

**Base URL**: `https://peaceful-inlet-88854.herokuapp.com/api`

<table>
    <tr>
        <th> Type </th> <th> Endpoint </th> <th> Parameters </th> <th> Description </th>
    </tr>
    <tr>
        <td> GET </td>
<td markdown="1">

`/employees`

</td>
        <td> None </td>
        <td> Returns a JSON array of all employees in the DB. </td>
    </tr>
    <tr>
        <td> POST </td>
<td markdown="1">

`/employees`

</td>
<td markdown="1">

Needs a body with a JSON object of the employee you wish to add.

```JSON
{
	"id":"15000",
	"name":"Test Person",
	"phone":"1234567890",
	"email":"test@devmounta.in",
	"title":"Tester"
}
```

</td>
        <td> Adds the employee listed (if the ID is not in use), returns a JSON array of all employees in the db. <br /> If the ID is already in use, should return an error.</td>
    </tr>
    <tr>
        <td> PUT </td>
<td markdown="1">

`/employees/:employeeID`

</td>
<td markdown="1">

| Type         | Key        | Value                                                       |
| ------------ | ---------- | ----------------------------------------------------------- |
| Path         | employeeID | The ID number of the employee to edit.                      |
| Query String | name       | The employee's current name, or desired new name.           |
| Query String | phone      | The employee's current phone number, or desired new number. |
| Query String | email      | The employee's current email, or desired new email.         |
| Query String | title      | The employee's current title, or desired new title.         |

</td>
        <td> Edits the employee with a matching ID to have the values provided. </td>
    </tr>
    <tr>
        <td> DELETE </td>
<td markdown="1">

`/employees/:employeeID`

</td>
<td markdown="1">

| Type | Key        | Value                                    |
| ---- | ---------- | ---------------------------------------- |
| Path | employeeID | The ID number of the employee to delete. |

</td>
        <td> Removes the employee with a matching ID. </td>
    </tr>
</table>

Here is an example collection you can import into Postman:

- <a href="./Employee_Manager.postman_collection.json" download>Employee Manager
  Collection</a>

## Step 1

1. Open the GET.
1. Open the "Tests" tab.
1. Add a snippet for `Status code: Code is 200`
1. Run the request, check the test results, `1/1` should pass.

Great! You have a working test.

- If you want to verify the test, change the expected code in the test to a
  different response code:

```javascript
pm.test("Status code is 200", function () {
  pm.response.to.have.status(300);
});
```

    * Now you should see the test fail.
    * Set the test back to looking for a `200`

## Step 2

1. Open the POST.
1. Open the "Tests" tab.
1. Add the following test: I started from the `Response body: JSON value check`

```javascript
pm.test("Your test name", function () {
  var jsonData = pm.response.json();
  var addedEmployee = jsonData.filter((emp) => emp.employee_id == 15000);
  pm.expect(addedEmployee).not.to.equal(undefined);
});
```

1. `addedEmployee` is now a variable we can use that should be the newly added
   employee.
1. Add more assertions looking at the other properties, verifying that the new
   employee has the right
   - Name
   - Phone number
   - Email
   - Title

> **Important**: This test adds a record, and will not work twice in a row as
> you cannot add two of the same record.
>
> - You can find a few solutions, but the easiest is likely to submit a request
>   (or use the UI) to delete the newly added employee before re-running the
>   test.
> - Keep in mind as well that in a shared environment your tests might clash
>   with another tester's - consider changing the ID to add/edit/delete a
>   different employee from other testers.

## Step 3

Add more testing

- Look in more detail/with additional tests in each requests
- Add testing for PUT and DELETE requests

## Stretch

Open the runner and run this collection of tests.

Experiment with reordering and see that running tests out of order (PUT before
POST for example) can cause problems.

## Solution

The collection with tests is available here as well.

- <a href="./Employee_Manager_with _tests.postman_collection.json" download>Employee
  Manager Collection - with tests</a>
