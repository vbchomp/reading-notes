# Class 02 - HTML, CSS and JS Some Loops
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
* Rules cascade, hence ccascade style sheets, so the last rule on the same type element wins
  * If there are two selectors on the p element, the last one is the one that gets executed
  * The more specific the selector wins, a header is less specific than third paragraph
* If using more than one page external CSS is handy to style all similar and reduces chances of making errors on multiple pages
    

## *JS Book* Chapter 2 - Basic JavaScript Instructions 


## *JS Book* Chapter 4 - Decisions and Loops
