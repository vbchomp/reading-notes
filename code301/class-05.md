# Class 05 - Putting it all together

[<== Main Page](../README.md)
[<== Code 301](../code301/code301.md)

## [Thinking in React](https://reactjs.org/docs/thinking-in-react.html)

- How would you break a mock into a component heirarchy?

- What is the single responsibility principle and how does it apply to components?

  A component should ideally do only one thing. If it grows, break up into smaller subcomponents.

- What does it mean to build a ‘static’ version of your application?

  Reuses components and passes data as props rather than state.

- Once you have a static application, what do you need to add?

- What are the three questions you can ask to determine if something is state?

  Is it passed from a parent via props? Does it remain unchanged over time? Can you compute it based on any other state or props in your component?

- How can you identify where state needs to live?

  Identify components that render based on that state. Find common owners. Either common owner or component higner in hierarchy should own. If cannot find a place where it makes sense to live, create a new component solely for holding state and add to hierarchy above the common owner component.

## Things I Want To Know More About
