# Class 06 - JS Object Literals; The DOM

[<== Main Page](../README.md)

## Problem Domain Article

[Understanding the Problem Domain is The Hardest Part of Programming](https://simpleprogrammer.com/understanding-the-problem-domain-is-the-hardest-part-of-programming)

## *JS Book* Chapter 3 - Object Literals (Pg 100-105)

- Objects take variables and functions and rename them as properties and methods
  - Properties tell us about the object,like a name or color
  - Methods are tasks, check number of available rooms in a hotel
- Properties and methods have names and values, name is a key
  - Objects cannot have more than one key with same name
  - Values of properties can be strings, numbers, boolean, array, or another object
  - Value of a method is always a function
  
- HTML uses attribute names and values
- CSS uses property names and values
- Each item in an array in JS has a name and value

```render-javascript

var hotel = {
  <--! These are properties down through roomTypes -->
  <!-- key: value -->
  name: 'Quay',
  rooms: 40,
  booked: 25,
  gym: true,
  roomTypes: ['twin', 'double','suite'],
  <!-- This is the method -->
  checkAvailability: function() { 
    return this.rooms - this.booked;
  }
};

```

- Literal notation creates objects, hotel object above created within {} and stored in the variable called hotel
  - this.room and this.booked uses the properties and values in this object
- Dot notation is used to access the properties or methods of an object
  - . is called member operator
  - object.property/method
`var hotelName = hotel.name;`
`var roomsFree = hotel.checkAvailability();`

- Can also use [] if properties have special characters like dashes, the name is a number, or a variable is used in place of the property name
`var hotelName = hotel['name'];`
`var roomsFree = hotel['checkAvailability']();`

## *JS Book* Chapter 5 - Document Object Model

- Not HTML or JS, own set of rules, implemented by browsers
- DOM specifies how browsers make a model of HTML page and how the JS will access and modify the page
  - Uses DOM Tree for structure, an object model, each object represents parts of the page
  - Defines methods and properties to access and update objects in model which updates what is seen in browser
  - Sometimes called an API (Application Programming Interface) which lets programs talk to each other

- DOM Tree model of web page
