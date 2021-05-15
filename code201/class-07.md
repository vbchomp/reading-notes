# Class 07 - JS Object Literals; The DOM

[<== Main Page](../README.md)

## Domain Modeling Article

[Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)

- Domain modeling creates conceptual models in code for a specific problem

- A constructor function defines the same properties among many objects. Setting up a constructor function

```render-javascript
// epicFailVideo constructor function
var epicFailVideo = function(epicRating, hasAnimals) {
  this.epicRating = epicRating;
  this.hasAnimals = hasAnimals;
};

var parkourFail = new epicFailVideo(7, false);
var corgiFail = new epicFailVideo(4, true);

console.log(parkourFail);
console.log(corgiFail);
```

## *HTML Book* Chapter 6 - Tables (126-145)

## *JS Book* Chapter 3 - Functions, Methods and Objects (106-144)
