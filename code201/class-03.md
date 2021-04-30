# Class 03 - HTML Lists, Control Flow with JS and the CSS Box Model

[<== Main Page](../README.md)

## *HTML Book* Chapter 3 - Lists

## *HTML Book* Chapter 13 - Boxes

## *JS Book* Chapter 2 - Basic JS Instructions

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

