# Pick the right data type: Objects vs Arrays

Object and Arrays are both useful, in their own space.

## Setup

In your `qa_playground/src` folder, create a new file, `objectsAndArrays.ts`

## Objects: Related but different

Objects are best when you want to store related pieces of data about a specific
thing; especially when you have different versions of that same thing.

In this file, create an object with three properties -- `firstName`, `lastName`,
and `age`. See the pattern below to follow.

```typescript
// objects are defined with this pattern:
var myObject = {
  //the curly brackets wrap the object
  key: "value", //the "properties" are key/value pairs
};
console.log(myObject.key); //the property's value is accessed with its key
// this would log: "value"
myObject.key = "a new value"; //you can edit values too, not just read them
console.log(myObject.key);
// now, this would log: "a new value"
```

Once you have your object, add the following code, replacing `x` with a
reference to your object.

```typescript
console.log(
  `Person:\n\t Name: "${x.firstName} ${x.lastName}" \n\t Age: ${x.age}`
);
// this is probably easier to read than:
// `Person:\n\t Name: "${x[0]} ${x[1]}" \n\t Age: ${x[2]}`
// while it works, using the object makes it more readable and maintainable
```

Your output should be something like:

```
Person:
         Name: "AJ Larson"
         Age: 33
```

---

## Arrays: Collections of the same type of thing

Arrays make the most sense when you have a list, or at least a collection, of
the SAME things.

- Favorite movies
- Names of employees
- Pizza toppings

They are, by default, ordered.

```typescript
// arrays are defined with this pattern:
var myArray = ["first", "second", "third", 4, true];
// square brackets wrap a comma separated list of whatever you're storing
// you can type an array:
var myTypedArray: Array<number> = [12, 654, 55, 23];
// and you access info in the array by its "index", which starts at 0
console.log(myArray[0]); // would log: "first"
console.log(myArray[4]); // would log: `true`
myTypedArray.push(3.14159); // this would allow us to add a number
```

In `objectsAndArrays.ts` add an array listing your favorite something:

- Books
- Movies
- Pizza toppings
- Times to nap

Now, add the following code and replace `x` with a reference to your array:

```typescript
x.forEach((thing, i) => {
  // a forEach can give back just each item in the array,
  // each item and the index,
  // or each item, the index, and the whole list
  console.log(`${i + 1}. ${thing}`);
});
```

This should print out a list something like the following:

```
1. Mint Cookie
2. Mint Chip
3. Cake Batter
4. Cookies and Cream
5. Cherry Garcia
```

---

## Using both!

Sometimes an array of objects is helpful.

- Maybe you have an array of "people", like the first object we created above.
- You could add the favorites list to your person object too.

Experiment with both!

I got mine to create the following outputs after I added an array of people, and
person with favorites...

```
Our object
====================
Person:
         Name: "AJ Larson"
         Age: 33

Our array
====================
1. Mint Cookie
2. Mint Chip
3. Cake Batter
4. Cookies and Cream
5. Cherry Garcia

An array of objects
====================
Person:
         Name: "AJ Larson"
         Age: 33
Person:
         Name: "Jane Doe"
         Age: 40
Person:
         Name: "John Doe"
         Age: 14

An object with an array
====================
Person:
         Name: "AJ Larson"
         Age: 33
         Favorite Ice Cream Flavors:
                Mint Cookie
                Mint Chip
                Cake Batter
                Cookies and Cream
                Cherry Garcia
```

---

## Solution

See the `2.03` branch of the `qa_playground` for solutions to today's practices.
