# Gain Through Inheritance

## Summary

Inheritance is a way that we can take an existing class and expand on it, using
what we already had and growing further. This exercise will be practicing using
inheritance and polymorphism.

We will start with an **Animal** class, and you'll see some TDD style tests that
describe two additional classes, **Fish** and **Bird**. These classes will need
to extend the Animal class and add some new functionality.

## Setup

1. Create a new test file. I set mine up in the `qa_playground` project.
1. Copy in the code in the popout below.

<details markdown="1"><summary><code>animalInheritance.test.ts</code></summary>

```typescript
class Animal {
  name: string;
  sound: string;
  food: string;
  constructor(name: string, sound: string, food: string) {
    this.name = name;
    this.sound = sound;
    this.food = food;
  }
  soundOff(): string {
    return `The ${this.name} makes the sound "${this.sound}".`;
  }
}

/**
 * Fish extends Animal, but takes different properties, has a different soundOff() method, and a new method, habitat().
 * @param {string} name - as expected
 * @param {string} food - as expected
 * @param {string} saltwater - true if the fish is a saltwater fish
 */

/**
 * Bird extends Animal, but takes an additional property, and has an additional method, fly().
 * @param {string} name - as expected
 * @param {string} sound - as expected
 * @param {string} food - as expected
 * @param {number} flightSpeed - the flight speed of the bird, in meters/second. This should be 0 for flightless birds.
 */

describe("Testing animals", () => {
  test("a basic animal works as expected", () => {
    let lion = new Animal("lion", "roar", "meat");
    // lion is an animal
    expect(lion instanceof Animal).toBeTruthy();
    // lion.soundOff() has the expected output
    expect(lion.soundOff()).toBe('The lion makes the sound "roar".');
  });
  describe("Fish", () => {
    // Fish should only have the three parameters listed.
    let goldfish = new Fish("goldfish", "pellets", false);
    let shark = new Fish("shark", "fish", true);
    it("are animals", () => {
      // Fish *must* extend Animal
      expect(goldfish instanceof Animal).toBeTruthy();
    });
    it("doesn't make sound", () => {
      // Fish should give the expected soundOff, it's own version
      expect(goldfish.soundOff()).toBe(
        "The goldfish is a fish and does not make sounds."
      );
    });
    it("can be saltwater or freshwater", () => {
      // Fish gives the right habitat string based on the `saltwater` property
      expect(goldfish.habitat()).toBe("The goldfish is a freshwater fish.");
      expect(shark.habitat()).toBe("The shark is a saltwater fish.");
    });
  });
  describe("Birds", () => {
    // Bird should actually take four arguments
    let swallow = new Bird("swallow", "chattering chirp", "insects", 11);
    let emu = new Bird("emu", "grunt", "plants and insects", 0);
    it("are animals", () => {
      // Bird *must* extend Animal
      expect(swallow instanceof Animal).toBeTruthy();
    });
    it("make sounds", () => {
      // Bird uses the standard soundOff
      expect(swallow.soundOff()).toBe(
        'The swallow makes the sound "chattering chirp".'
      );
    });
    it("might be able to fly", () => {
      // Bird have a new method using the fly speed to give us these strings
      expect(swallow.fly()).toBe(
        "The swallow flies at speeds of up to 11 meters per second!"
      );
      expect(emu.fly()).toBe("The emu is a flightless bird.");
    });
  });
});
```

</details>

## Step 1: Add the Fish Class

You'll need to add a new class, `Fish` to pass the first nested `describe`,

> `describe("Fish", ()=>{`

with its tests that check the class. You have a JSDoc comment for the class, and
also the tests to review that show us the requirements below:

### `Fish` Requirements:

1. A `Fish` must be an `Animal`
1. `Fish.soundOff()` is different than `Animal.soundOff()`, see the expects for
   the specifics.
1. It has a new method, `Fish.habitat()` that reveals if the `Fish`It must have
   a property for being salt water or not

### Process:

1. Declare the extended class
1. Define any additional properties (`saltwater`)
1. Set up its constructor method
   - This needs to call `super(/* pass the parent class's parameters here */)`
     first thing to use the parent class's constructor.
1. Define any methods that will override parent methods (`soundOff`)
1. Define any new methods (`habitat`)

---

## Step 2: Add the Bird Class

This will work the same as the Fish Class, but the requirements are simpler.

### `Bird` Requirements:

1. A `Bird` must be an `Animal`.
1. `Bird.soundOff()` should work the same way as `Animal.soundOff()`
1. `Bird.fly()` is a new method that keys off of the `flightSpeed` parameter.

This should follow the same process as `Fish`.

---

## Stretch

To push a bit further, consider expanding `Fish` to have multiple sub-classes of
its own!

---

## Solution

See the solution with comments, `solutions/2.08/gainThroughInheritance.test.ts`
in the `2.08` branch of `qa_playground`
