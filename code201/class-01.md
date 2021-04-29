# Class 01 - Introductory HTML and JS

[<== Main Page](../README.md)

## *HTML* Chapter 1 on Structure

* HTML tags are containers with info about the items inside the tags
* Tags and elements are commonly used interchangeably
  * An element really encompasses everything from the opening tag to the end of the closing tag
* An attribute is placed in the opening tag and has a name and a value
  * `<p class="family">`

## *HTML* Chapter 8 on Extra Markup

* :sparkles: just to practice my markdown emojis
* Commenting is beneficial to others who read your code after you!!!
  * Commenting also allows you to remember why you did this thing for that reason 3 years from when you wrote it
  * Comments are viewable in the source code by using the following in HTML
    * `<!-- comments go in here -->`
* A few types of markups
  * id attribute assigns unique identity to an element and allows css to work against just that element
  * class attribute assigns several elements to a class and allows css to work against those elements
  * div groups elements together in a block, think lists
  * span groups elements together inline, think TBD
  * iframe is usually maps and other windows cut into page
  * meta element contains page information and is used to supply info about page to search engines
  * escape characters are special codes to enter before characters that have special meaning to programming languages

## *HTML* Chapter 17 on HTML5 Layout

* :camel: more emoji practice
* HTML5 introduced a new set of elements to minimize the amount of redundant words? in code
* The elements decribe the content of the item instead of the element name and attribute
  * article element could stand alone 
  * aside in article is like a quote pertaining to article
  * aside outside article then it relates to whole page
  * sections each have their own headings, may contain more than one article with common theme
  * hgroup groups heading elements
  * div used for groups of elements that have no other useful grouping
* Older browsers need CSS to interpret the HTML5 as block level elements instead of rendering as inline
* JS is available on Google to help IE8 and older interpret HTML5

## *HTML* Chapter 18 on Process & Design

* Understand your target audience, why the visit, what they want, will they return
* Making a site map helps organize pages logically
* Wireframes allows you to organize pages visually, what goes where
* Use size color and styles to grab/direct attention  
* Group similar items together and stay consistent
* Use clear, concise, interactive, and consistent navigation

## *JS* Chapter 1 on ABC of Programming

* :tada: I missed one on my last chapter

### Chapter 1a What is a script and how do I write one?

* A script is a set of instructions that computer uses to do something - think recipe
* Start by identifying your end goal, then identify steps or task to complete the goal, then code each piece
* Make a flowchart

### Chapter 1b How do computers fit in with world around them?

* Computers use data to model things
* Everything is an object, each object has properties, events change the properties of objects, methods retrieve or update values of object's properties

### Chapter 1c How do I write a script for a web page?

* HTML is the content and gives structure, CSS makes it pretty, JSS controls actions
* Best practice to keep separate files of each language, .html, .css, .js
