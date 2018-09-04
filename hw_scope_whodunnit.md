# Scope Homework: Who Dunnit

### Learning Objectives

- Understand function scope
- Know the difference in between the `let` and `const` keywords

## Brief

Using your knowledge about scope and variable declarations in JavaScript, look at the following code snippets and predict what the output or error will be and why.

### MVP

#### Episode 1

```js
const scenario = {
  murderer: 'Miss Scarlet',
  room: 'Library',
  weapon: 'Rope'
};

const declareMurderer = function() {
  return `The murderer is ${scenario.murderer}.`;
}

const verdict = declareMurderer();
console.log(verdict);
```
<!--
chloe - will declare that miss scarlet is the murderer -->


#### Episode 2

```js
const murderer = 'Professor Plum';

const changeMurderer = function() {
  murderer = 'Mrs. Peacock';
}

const declareMurderer = function() {
  return `The murderer is ${murderer}.`;
}

changeMurderer();
const verdict = declareMurderer();
console.log(verdict);
```

<!-- chloe - wont work as trying to assign a new murderer.  will error. -->

#### Episode 3

```js
let murderer = 'Professor Plum';

const declareMurderer = function() {
  let murderer = 'Mrs. Peacock';
  return `The murderer is ${murderer}.`;
}

const firstVerdict = declareMurderer();
console.log('First Verdict: ', firstVerdict);
//
// chloe - first verdict will be mrs Peacock

const secondVerdict = `The murderer is ${murderer}.`;
console.log('Second Verdict: ', secondVerdict);

// chloe -second verdict will be professor plum as its outside the funct
```

<!-- chloe - let will allow you to reassign who the murderer is so will change from
        Professor plum to mrs Peacock -->


#### Episode 4

```js
let suspectOne = 'Miss Scarlet';
let suspectTwo = 'Professor Plum';
let suspectThree = 'Mrs. Peacock';

const declareAllSuspects = function() {
  let suspectThree = 'Colonel Mustard';
  return `The suspects are ${suspectOne}, ${suspectTwo}, ${suspectThree}.`;

  // chloe - will retuern all suspects and chance suspect 3 to colonel mustard
}

const suspects = declareAllSuspects();
console.log(suspects);
console.log(`Suspect three is ${suspectThree}.`);

// chloe - will show suspect 3 as mrs peacock as it is outside the fuction and not
// let you further edit any suspects as it is then changed to a const & cannot edit.


```

#### Episode 5

```js
const scenario = {
  murderer: 'Miss Scarlet',
  room: 'Kitchen',
  weapon: 'Candle Stick'
};

const changeWeapon = function(newWeapon) {
  scenario.weapon = newWeapon;

//objects can be amended with const as long as its still an object
//if you were to declare new object with weapon: 'revolver' wouldnt work.

}


const declareWeapon = function() {
  return `The weapon is the ${scenario.weapon}.`;
}

changeWeapon('Revolver');
const verdict = declareWeapon();
console.log(verdict);

//will return weapon as revolver as data can be manipulated

```

#### Episode 6

```js
let murderer = 'Colonel Mustard';

const changeMurderer = function() {
  murderer = 'Mr. Green';

  //murderer now changed to mrs green as let allows you to change it.

  const plotTwist = function() {
    murderer = 'Mrs. White';
  }
// plot twist murderer is mrs white different function and can be seen outside of block
  plotTwist();
}

const declareMurderer = function () {
  return `The murderer is ${murderer}.`;
  //reassigning variable to a new object so will return mrs white as murderer
}

changeMurderer();
const verdict = declareMurderer();
console.log(verdict);

//found this hard to follow

```

#### Episode 7

```js
let murderer = 'Professor Plum';

//let can be edited

const changeMurderer = function() {
  murderer = 'Mr. Green';

  //murderer is now mrs green

  const plotTwist = function() {
    let murderer = 'Colonel Mustard';

//murderer is now Mustard as assigning to different object.

    const unexpectedOutcome = function() {
      murderer = 'Miss Scarlet';
    }


    unexpectedOutcome();
    //murderer is now mrs scarlet and cannot be changed
  }

  plotTwist();

  // murderer is now Mustard
}

const declareMurderer = function() {
  return `The murderer is ${murderer}.`;
    // murderer is now Mustard
}

changeMurderer();
const verdict = declareMurderer();
console.log(verdict);

//changemurderer is now called so the function will return the murderer is mrs green.
// as her function is named 'change murderer'
```

#### Episode 8

```js
const scenario = {
  murderer: 'Mrs. Peacock',
  room: 'Conservatory',
  weapon: 'Lead Pipe'
};

// info inside object  can be manipulated not the object itself.

const changeScenario = function() {
  scenario.murderer = 'Mrs. Peacock';
  scenario.room = 'Dining Room';

// will error as you are trying to change the object to something else. this code
//is obsolite

  const plotTwist = function(room) {
    if (scenario.room === room) {
      scenario.murderer = 'Colonel Mustard';
    }
//manipulationg infornation inside the object so murderer is now Mustard
    const unexpectedOutcome = function(murderer) {
      if (scenario.murderer === murderer) {
        scenario.weapon = 'Candle Stick';
      }
    }
//manipulating information so weapon is now candle stick
    unexpectedOutcome('Colonel Mustard');
  }

  plotTwist('Dining Room');

  //assigning room to be dining room
}

const declareWeapon = function() {
  return `The weapon is ${scenario.weapon}.`
}


changeScenario();
const verdict = declareWeapon();
console.log(verdict);

// will show weapon as a candle stick

```

#### Episode 9

```js
let murderer = 'Professor Plum';

//let allows you to edit information

if (murderer === 'Professor Plum') {
  let murderer = 'Mrs. Peacock';
}

//if murderer is equal to professor plum which it is change murderer to mrs peacock but only exists inside the function
//so will end after the } close bracket and will change back to professor plum

const declareMurderer = function() {
  return `The murderer is ${murderer}.`;
}


const verdict = declareMurderer();
console.log(verdict);
//will decalre murderer professor plum


### Extensions
Make up your own episode!



const scenario = {
  murderer: 'Sandy',
  room: 'e24 classroom',
  weapon: 'Javascript'
};

const declareMurderer = function() {
  return `The murderer is ${scenario.murderer} with ${scenario.weapon}.`;
}

const verdict = declareMurderer();
console.log(verdict);
