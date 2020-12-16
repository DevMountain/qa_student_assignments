# Generate Test Data via API Request

#### Target Time +/- 15 minutes

## Summary

Save some data from an API request and use it as test data!

## Setup

Add the following test to an existing testing project, like your
`qa_playground`.

- This test will cycle through all items in the employees array, and run a test
  for each.
- We're expecting that all employees in that array are visible in the UI.

```typescript
import { EmployeeManager } from "./pageObjects/EmployeeManager";

const page = new EmployeeManager("chrome");

// your data will go in this variable
const employees = [];

describe("checking that the UI matches the DB", () => {
  beforeEach(async () => await page.navigate());
  afterAll(async () => await page.driver.quit());
  for (let i = 0; i < employees.length; i++) {
    test(`Looking for ${employees[i].employee_name} in the UI`, async () => {
      await page.selectEmployee(employees[i].employee_name);
      let employee = await page.getCurrentEmployee();
      expect(employee.id).toEqual(employees[i].employee_id.toString());
      expect(employee.name).toEqual(employees[i].employee_name);
      expect(employee.phone.toString()).toEqual(employees[i].employee_phone);
      expect(employee.email).toEqual(employees[i].employee_email);
      expect(employee.title).toEqual(employees[i].employee_title);
    });
  }
});
```

## Step 1

Execute a query in Postman to get all the employees in the Employee Manager v2
database.

- <a href="./sp2.09.2.html" target="\_blank">"Test API Requests"</a> has the
  request you need if you're missing it.

## Step 2

1. Copy the response; an array of employee objects.
1. Paste it in place of the "employees" array.

## Step 3

Run your test.

- `npx jest testname`
- It should pass; if it doesn't, was someone else using the database in the
  interim so your data is out of date?

## Step 4

Consider; what benefits can come from testing like this?

- What are the risks?

## Stretch

Looking at the GET in Postman, there is a "Code" link to the side...

- Try and copy the JS code for the request and see if you can use the return for
  the test!

## Solutions

See `/solutions/2.09` in the `2.09` branch of `qa_playground`

- `postmanData.test.ts` for the basic test (data may be out of date)
- `apiPostmanData.test.ts` for the test with the api call that should use up to
  date data automatically
  - you will need to use `npm i` to install the updated dependencies for this
    test to pass
