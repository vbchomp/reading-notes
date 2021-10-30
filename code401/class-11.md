# Class 11 - Event Driven Applications

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Why is access control important? It follows the least-privilege principle. This is a security principle that says a person can only access the lowest access that they need to do their job. They do not need to have root level privileges to create a table in a database. However, someone might become a victim of coercion or become an inside threat if given too much access.

- Describe an application that would need access control. A database that controls personnel and pay information.

- What is a role used for? To differentiate at what levels users can view and manipulate data in systems.

- Why is role based access control more scalable than discretionary or mandatory access control? Roles are centrally managed and can be used in security groups, where DAC is set on objects like files and MAC is normally set by the organization and you normally have no control over who has access. RBAC can be scaled up or down based on the groups. [Role-Based Access Control](https://www.sciencedirect.com/topics/computer-science/role-based-access-control)

## Additional Resources

- [Event-Driven Programming in Node.js](https://www.digitalocean.com/community/tutorials/nodejs-event-driven-programming)

- [Node.js v17.0.1 documentation](https://nodejs.org/api/events.html)

## Videos

## Vocab

- Authorization allows you access to parts of a system based on what job or role you have been assigned.

- Role Based Access Control assigns your access based on what role you are assigned in the company to prevent role over-reach. [Role-based access control](https://en.wikipedia.org/wiki/Role-based_access_control)

- Capabilities are the assignments that users can do based on the roles or jobs they are assigned, like create a table or delete a user. [Capability-based security](https://en.wikipedia.org/wiki/Capability-based_security)

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?
- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- curried functions

- Class notes

- Emitter does something sends 

- Listener listens for something, but maybe not for the event the emitter is doing. Might need to wait for a different emitter.

- create a chat app

- Event pool
Events: user has been added to chat, messages, content, DM, share, online status, mouse movement, minimize

export event pool

- Chat room
require events from event pool

Listeners
    messages
    user added

- Users

module.exports = {all the events}

- Admin Log
require events from the event pool

ALL THE LISTENERS!!!

listeners

- User Icon

Listeners
Online Status


- How to modularize the demo

- touch event-pool.js brain.js(brain.js)

event-pool.js
'use strict';

const Events = require('events');
const events = new Events();

// Export ONE instance of events that all modules can share
// this is called a ... "singleton"
// Think of it as a global variable that all the modules can see and use
module.exports = events;


brain.js since demo is pupil, eye, or server.js
'use strict';

// Event Hub

const events = require('./event-pool.js');

// Require our body parts, users, carts, fogs, catmodels ... they will hear our events
require('./body-parts/arms/arms.js');
require('./body-parts/eyes/eyes.js');

// For now, we're a dumb brain, only caring about a single event.
// this one, comes to us from the eyes every time they blink.
// When it happens, we need to tell the rest of the body the new brightness
// so that each part can respond as it feels like

// The event handler takes in an event, and a callback to run.
// Callback can be writen inline as shown, or as a reference to a function
events.on('light-detected', (payload) => {
  events.emit('light', { brightness: payload })
});

- mkdir body-parts 
cd body-parts
touch eyes.js arms.js

'use strict';

const events = require('./event-pool');
const handlers = require('./arms-handlers.js');

// The brain will emit a "light" event with some payload ... here's how the arms handle that
// Note, the arms module probably cares about a billion other events ...
// Note, also that we've pulled in the callback function from a separate module
events.on('light', handlers.coverEyes);

or 
//events.on('light', handlers.coverEyes);

arms-handlers.js
'use strict';

function coverEyes(payload) {
  if (payload.brightness >= 90) {
    console.log('Covering Eyes');
  }
}
module.exports = { coverEyes }

- this is a tool so it goes in the lib or util

- caps.js is same as index.js for this lab
front facing
// require evenets and modules
const events = require('./util/event_pool.js);
const vendor = require('./modules/vendor.js);

// const driver

// event listeners => callback
// event pickup
// event delivered
// event in-trnsit
events.on('pickup', (payload) => logEvent('pickup', payload));

// callback function
function logEvent(event, payload) {
    //console log event, time, payload

}


- vendor.js
'use strict'

const events = require('../util/event-pool.js');
const faker = require('faker');

// delivery variable => <- store, order ID, customer, adderss
setInterval(() => {
    let delivery = {
        store: 'Strong Days',
        oderID: faker.uuid(),
        customer: `${faker.name.firstName()} ${faker.name.lastName}`,
        address: //'town and state using faker'
    }
    events.emit('pickup', delivery);
}, 5000);

// listen for delivered event => handleDelivery

// 

- touch driver.js