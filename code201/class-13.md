# Class 13 - Local Storage

[<== Main Page](../README.md)

## [No 7. The Past, Present & Future of Local Storage for Web Applications](http://diveinto.html5doctor.com/storage.html)

- Cookies! were invented early to try to fix persistent local storage of small amounts of data. Had 3 downsides.
  - Included with every HTTP request by repeatedly transmitting the same data over and over.
  - Included with every HTTP so sent unenecrpted data, unless entire application was using SSL
  - Limited to 4kb of data, slow application, but not very useful.

- What do we want?
  - lots of storage space
  - on the cient machine
  - persistent beyond page refresh
  - not transmitted to server

- Brief History of Local Storage before HTML5
  - Microsoft tried to win the browser wars with DHTML and userData, which allowed pages to store 64kb in an XML structure
  - Adobe comes out with Flash 6, named Flash Cookies aka Local SHared Objects. Allows 100kb of data per domain stored.
  - Google tried Gears, provides an API to an embedded SQLite database, with unlimited storage once permission from user is granted once.
  - All the solutions were specific to a browser or reliant on plug-ins.

- Dunh, dunh, dunh...HTML5 Storage!
  - Web Storage, Local Storage or DOM Storage.
  - Able to store named key/value pairs locally, persitent after page navigation, closing browser tab, exiting browser, etc. 
  - Not transmitted across server like cookies.
  - Available even when third-party plug-ins are not.
  - IE8+, Firefox 3.5+, Safari 4.0+, Chrome 4.0+, Opera 10.5+, iPhone 2.0+ and Android 2.0+.

- Access is through JS code using the localStorage object in the global window object. 

- Checks whether browser supports it.

```render-javascript
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```

- Or user Modernizr to detect

```render-javascript
if (Modernizr.localstorage) {
  // window.localStorage is available!
} else {
  // no native support for HTML5 storage :(
  // maybe try dojox.storage or a third-party solution
}
```

## Class Notes

- Class 15 has project rubric
  - 3 pages - about me with no js, just bios and github/linkedIn
  - Landing page, index.html
  - Constructor, user input, event listener, use the user input,

- Local Storage is saved on the client machine, typically C drive
  - stringify (json aka JS Object Notatation) data to get it ready to store to local
  - parse stringified data when it comes out of local storage
  - In dev tools, let students = 42
  - `localStorage.setItem('name', value);`
  - `localStorage.getItem('name');`
  
- `let stringifiedStudent = JSON.stringify(student);`
  - `localStorage.setItem('person', student);`
  - `let retrievedStudent = localStorage.getitem('person');`
  - `let parsedRetrievedStudent = JSON.parse(retrievedStudent);`

- Goats
  - after clicks allowed and render chart, then stringify and save to local
  - to get storage 
  let retireved =  getItem
  if retrievedgoats exists
  run parse
  else instantiate
  - this prevents duplicates
