# Class 10 - JS Debugging

[<== Main Page](../README.md)

## *JS Book* Chapter 10

- Order of execution refers to how Js will execute lines of code. It is not necessarily 1, 2, 3. It could be 2, 3, 1.

- Execution contexts are either global and used by all pages, or functions and used only by those functions.

- Variable scope is where variables can be used, global or function-level.

- Hositing is calling a function before it is declared or assigning a value to a variable that has not been declared.

- Error handling can help identify what to do if errors happen. If not error handling is found, script stops and error object is created.
  - Error Obj has name, message, fileNummber and lineNumber.

- Seven types of error objects, Error, SyntaxError, ReferenceError, TypeError, RangeError, URIError, EvalError.
  - Generic error object which does not have a template.
  - Syntax is not correct, like missing a ) or ;
  - Reference means variable or function not defined.
  - Type is value is unexpected data type.
  - Range is where number is outside of range.
  - URI is incorrect use of URI functions and special characters not escaped.
  - Eval is incorrect use of eval functions.
  - NaN is not an error it happens when trying to perform math on strings.

- You can either debug script or handle errors gracefully
- Debugging, where is it?, what is it?
  - Console methods, console.info() general info, console.warn() warnings, console.error() used to hold errors.
  - Console.table(tableName);
  - Breakpoints pauses script to check values stroed in variables at that time.
  - Then you can step through the code breakpoint to breakpoint.
- Handling errors, try, catch. finally

```render-javascript
try {
  // try to execute this code
} catch (exception) {
  // If there is an exception, run this code
} finally {
  // This always gets executed
}
```

- Throwing errors generate errors instead of waiting for the interpreter to.

- To prevent bugs altogether
  - be willing to make mistakes
  - proof of life, often, visual testing
  - have a working linter
  - rely on our tools
  - console log things, or other console methods
  - test in console for proof of life
  - break points - to analyze your code
  - error handling

- How do we debug? Tips and Tricks!
  - Identify problem, where is problem
  - 2nd opinion, set of eyes
  - run piece by piece even is you have comment everything out and move forward step by step
  - change pperspective, relax, take breaks
  - trial and error
  - look in console, line and space where error occurs
  - google/stack overflow or mdn docs for js, maybe w3schools for css
  - going through your process, call stack, confirm things happen in correct order
  - save - ACP OFTEN - working sources of truth
  - RTFM
