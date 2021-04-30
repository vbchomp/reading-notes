# Class 03 - HTML Lists, Control Flow with JS and the CSS Box Model

[<== Main Page](../README.md)

## *HTML Book* Chapter 3 - Lists

- Ordered lists have numbers (can be reversed), unordered lists start with bullet points and definition lists are vocab words and definitions

- Can be styled in css using type attribute

- Definition list created using `<dl>` element

```render-html
<dl>
  <dt>My House</dt>
  <dd>The place where I live.</dd>
  <dt>Your House</dt>
  <dd>The place where you live.</dd>
 </dl>
 ```

- Nested lists are created by adding indents 

```render-html
<ul>
  <li>Dogs</li>
  <li>Cats
    <ul>
      <li>Yours</li>
      <li>Mine</li>
    </ul>
  </li>
  <li>Birds</li>
</ul>
```

## *HTML Book* Chapter 13 - Boxes

- Boxes are sized to hold it's contents by default. The size can be adjusted by height and width. Can also adjust the elements inside the boxes.

- Minimum and maximum heights and widths can be adjusted to fit in browsers.

- Overflow content can be handled by hiding or scrolling.

- Borders, padding and margins are properties that control how a box looks.

  - Borders separate the edges of each box from other boxes.

  - Margins are outside the edge of the border.

  - Padding if the space between the border and the content inside box.

- Border width properties use px or thin, thick, medium values on top, left, right and bottom

- Border style properties are solid, dotted, dashed, grooved, ridged, inset, outset, hidden/none

- Border colors are just as numberous as the colors for everything else

- Start at pg 314 for rest of notes!

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
