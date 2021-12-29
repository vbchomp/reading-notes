# Class 28 - Component Lifecycle / useEffect()

[<== Main Page](../README.md)
[<== Code 401](../code401/code401.md)

## Readings

- Why do we not need more .html pages in a multi-page React app?

React only needs the index.html to run.

- If we wanted a component to show up on every page, where would we put it and why?
  - Inside the <BrowserRouter />, outside a <Route /> 

- What does routing do with the components that were rendered when a new route is requested

It only renders the components in the new route.

- What does props.children contain?

Contains whatever is included in the opening and closing tags when invoking a component. [What is {this.props.children} and when you should use it?](https://stackoverflow.com/questions/49706823/what-is-this-props-children-and-when-you-should-use-it)

- How do useState() and this.setState() differ?

setState sets the state objects in class components and useState is a hook in React that can use state without creating a class. [useState() vs setState() - Strings, Objects, and Arrays](https://dev.to/johnstonlogan/react-hooks-barney-style-1hk7)

## Additional Resources

[Using the Effect Hook](https://reactjs.org/docs/hooks-effect.html)  

## Videos

## Vocab

- State Hook is a function that allows you to use state without writing a class. [Using the State Hook](https://reactjs.org/docs/hooks-state.html)

- Mounting is the lifecycle phase where the component mounts on the DOM. [How to understand a component’s lifecycle methods in ReactJS](https://www.freecodecamp.org/news/how-to-understand-a-components-lifecycle-methods-in-reactjs-e1a609840630/)

- Un-Mounting is the last lifecycle phase and unmounts from the DOM. See mounting reference.

## Bookmark/Skim

- Which 3 things had you heard about previously and now have better clarity on?
- Which 3 things are you hoping to learn more about in the upcoming lecture/demo?
- What are you most excited about trying to implement or see how it works?

## Things I Want To Know More About

- Class notes
