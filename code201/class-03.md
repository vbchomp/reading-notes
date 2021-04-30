# Class 03 - HTML Lists, Control Flow with JS and the CSS Box Model

[<== Main Page](../README.md)

## *HTML Book* Chapter 3 - Lists

## *HTML Book* Chapter 13 - Boxes

## *JS Book* Chapter 2 - Basic JS Instructions

- Arrays store lists of values
  
```render-javascript
var dogs;
dogs = ['mutt', 'husky', 'heeler', gsd', 'yorkie'];
```

- Array index starts at 0, so 5 dog list is array with [4]

  - Re-assign value in spot 5 of array `dogs[4] = 'ankleBiter';`

## *JS Book* Chapter 4 - Decisions and Loops

- If...Else Statements evaluate a condition

  - If it resolves to *true* the first code block executes
  - If it is *false* the second code block executes

  - All statements are checked even if a match is found

```render-javascript
  if (pass >= 70) {
     congratulate();
  }
  else {
     encourage();
  }
  ```

- Switch statements evaluate whether the variable (switch value) matches a set of options of code that would run if the value matches

  - If the switch value does not match, the default value option is run

  - Provides better performance than multiple if statements

```render-javascript
switch (level) {

  case 'One':
  title = 'Level 1';
  break;

  case 'Two':
  title = 'Level 2';
  break;

  case 'Three':
  title = 'Level 3'
  break;

  default:
  title = 'Test';
  break;
  
}
```

- JS uses weak typing and converts data types (called type coercion) to complete operations. 

  - Use `=== and !===` (strict equality) rather than `== and !==` and JS will give you less data type errors

- Truthy (commonly 1) and falsy (commonly 0) values are caused by type coercion

  - Falsy values: boolean false, number zero, empty string, NaN, a variable with no value assigned

  - Truthy values: boolean true, numbers other zero, strings, number calculations, true written as string, zero written as string, false written as string 

- Need to get more infor on Short circuit values (JS Book, 169)

- Loops run if a condition returns true, then keeps checking and running until it returns false

  - For  loops run a specific number of times
  
  - While loops run while a specific condition is true
  
  - Do while loop, like while, but will run at least once, even if condition is false

  - Loop counters `for (var i = 0; i <4; i++) {`

  - document.write(); writes to page
