# Class 02 - HTML, CSS and some JS Loops

[<== Main Page](../README.md)

## *HTML Book* Chapter 2 - Test

* HTML tags for heading and paragaphs `<h1></h1>` or `<p></p>` are structural
* Tags affecting fonts like `the word <b>bold</b>` or `the word <i>italic</i>`
  * These tags work for super and sub scripts `4<sup>th</sup> of July` and when `providing footnotes<sub>3</sub>` 
* White space in HTML is not rendered on the web page 
* Use `<br />` for a line break or `<hr />` for an actual line between elements
  * These are empty elements and do not need a closing tag
* Content Management systems have visual editors that look like word processors and code views
* Semantic markup provides additional information on page for accessibility
  * Tags include `<strong>, <em>, <blockquote>, <q>, <abbr>, <cite>, <dfn>, <address>, <ins>, <del>, <s>`  

## *HTML Book* Chapter 10 - Introducing CSS

* CSS creates rules that control how elements look
  * Selector is the HTML element the rule applies to
  * Declaration styles the element with a property and property value
  * `p   {font-family: Courier;}
  * selector {property: value;}
* External CSS uses the styles.css file
* Internal CSS uses the `<style></style>` element in the HTML file
* Selectors are case sensitive, so must match exactly
  * Universal targets all elements on page `* {}`
  * Type targets just those elements `h1, h2, h3 {}`  
  * Class targets class attributes with values matching after period `.wicked {}` `p.wicked {}` targets p elements with wicked class attribute
  * ID targets id attributes with values after number sign `#wego {}`
* Rules cascade, hence cascade style sheets, so the last rule on the same type element wins
  * If there are two selectors on the p element, the last one is the one that gets executed
  * The more specific the selector wins, a header is less specific than third paragraph
* If using more than one page external CSS is handy to style all similar and reduces chances of making errors on multiple pages

## *JS Book* Chapter 2 - Basic JavaScript Instructions 

* Scripts are instructions, or statements, that computers use to complete tasks
* Each statement should end with a semicolon
* Comments explain what code does, allows others to figure out your logic
  * JS multi-line comments `/* comments go here on more than one line */`
  * JS single line comments `// Just this line will be commented out `
* Variables store temporary data
  * Declared by `var variablename;`
  * Assigned by `variablename = value;` 
  * Variables can contain letters, numbers, $ amd _
  * useCamelCaseToNameVariableWithMoreThanOneWord
* Data types can be numbers, text or boolean
* Arrays can create lists of related values
  * Each item is given a number starting at 0, so 5th array item is actually numbered as `[4]`
  * `// Example of creating an array`
  * `var simpsons;`
  * `simpsons = ['homer', 'marge', 'baart', 'lisa', 'maggie'];`
  * `// Realized misspelled bart. Will update with bart, which is basically reassigning it another value`
  * `simpsons[2] = 'bart';`

## *JS Book* Chapter 4 - Decisions and Loops

* Comparison operators evaluates two or more values to determine if they are the expected value returns true or false
  * `== is equal to, != is not equal to, > greater than, < less than, >= greater than or equal to, >= less than or equal to`
  * `=== strict equal to, !== strict not equal to` comparees value AND data types to see if they are true
* Logical operators compare results from more than one comparison operator
  * `&&` Logical AND returns true if both expressions are true `((5 , 2) && (2 >= 3))`
  * `||` Logical OR returns true if either exp are true `((2 < 5) || (2 < 1))`
  * `!` Logical NOT returns true if it was false `!(2 < 1)`
* If statements allow blocks of code to run if statements are true 

## How To Write a Git Commit Message - Chris Beams
