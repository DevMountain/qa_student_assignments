# SQL Testing Checklist

#### Target Time +/- 60 minutes

## Summary

In this project, we'll be practicing inserting and querying data using SQL.
We'll make use of an online database emulator tool found
<a href="https://postgres.devmountain.com/">Here</a>. Careful, if you reload the
page your changes will be lost.

### Tool Use

**Structure**

- On the left of the tool are the Tables with their fields/schema.
- The input area on the right is where we will be writing our queries.
- The play button in the corner runs queries.
- The bottom is where we will see our results (or errors).

**Nice to Know**

- The dropdown above has some example queries you can look through.
- CTRL + Enter or CMD + Enter will submit a query if you don't want to have to
  click the "play" button.

---

## Challenge 1

SELECT all the data FROM the artist table.

<details>

<summary> <code> SQL Solution </code> </summary>

```sql
SELECT * FROM artist;
```

</details>

---

## Challenge 2

SELECT the first_name, last_name, and country FROM the employee table.

<details>

<summary> <code> SQL Solution </code> </summary>

```sql
SELECT first_name, last_name, country
FROM employee;
```

</details>

---

## Challenge 3

SELECT the name, composer, and milliseconds FROM the track table WHERE the
milliseconds are greater than 299000.

<details>

<summary> <code> SQL Solution </code> </summary>

```sql
SELECT name, composer, milliseconds
FROM track
WHERE milliseconds > 299000;
```

</details>

---

## Challenge 4

SELECT all customers who have a company listed in their profiles, or rather,
where their row's company value is not `null`.

<details>

<summary> <code> SQL Solution </code> </summary>

```sql
SELECT *
FROM customer
WHERE company IS NOT NULL;
```

</details>

---

## Submission

Submit the queries you used, along with any queries you were able to figure out
from the stretch queries. Copy and paste or a doc work just fine.

---

## Stretch

Now that we have some basic query examples. Let's try doing some more
complicated ones. Use [www.sqlteaching.com](http://www.sqlteaching.com/) or
[sqlbolt.com](http://sqlbolt.com/) as resources for the missing keywords you'll
need.

1. Find the average length of all tracks in milliseconds
2. Find the number of invoices in the USA
3. Make a list of all the First Names of Customers that contain an 'a'
4. Make a list of the 10 longest tracks
5. Make a list of the 20 shortest tracks
6. Find all the customers that live in California or Washington
7. Find all the customers that live in California, Washington, Utah, Florida, or
   Arizona (Use IN keyword)
8. Insert an artist to the database
9. Insert yourself as a customer to the database
10. Find a list of all Playlists that start with `Classical`
11. You can either continue exploring this dataset or look into setting up
    postgres on your local machine.

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and
create a pull request so we can review your changes and merge them into the
master repo and branch.

## Copyright

© DevMountain LLC, 2017. Unauthorized use and/or duplication of this material
without express and written permission from DevMountain, LLC is strictly
prohibited. Excerpts and links may be used, provided that full and clear credit
is given to DevMountain with appropriate and specific direction to the original
content.

<p align="center">
<img src="https://s3.amazonaws.com/devmountain/readme-logo.png" width="250">
</p>
