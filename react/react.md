# React notes

## Background for understanding React

### The use of pure functions

In computer science, a pure function is a function which:

1. When given the same input, a pure function will **ALWAYS** return the same output
2. Has no side effects (altering of external states)
3. Does not rely on any external state

### Virtual DOM

Pete Hunt's (Facebook) talk on virtual DOM: [https://www.youtube.com/watch?v=-DX3vJiqxm4](https://www.youtube.com/watch?v=-DX3vJiqxm4).

- The virtual DOM is a fast, in-memory representation of the real DOM.
- The virtual DOM is an abstraction that allows us to treat JavaScript and DOM as if they were reactive. 
- You don't need to worry about what actually needs to be re-rendered. React allows you to write your code as if you were re-rendering the entire DOM every time your application's state changes.

#### How it works

1. Whenever the state of your data model changes, the virtual DOM and React will re-render your UI to a virtual DOM representation.
2. React then calculates the difference between the two virtual DOM representations: the previous virtual DOM representation that was computed before the data was changed and the current virtual DOM representation that was computed after the data was changed. This difference between the two virtual DOM representations is what actually needs to be changed in the real DOM.
3. React updates only what needs to be updated in the real DOM.
The process of finding a difference between the two representations of the virtual DOM and re-rendering only the updated patches in a real DOM is fast. 

## React

### `React` object
- All of the APIs available to you are accessible via this object
- The API surface area is intentionally small

### `ReactDOM` object
It has only a handful of methods, the `render()` being the most useful. These methods used to be part of the React object, but since version 0.14, they are separated to emphasize the fact that the actual rendering of the application is a separate concern. You can create a React app to render in different environments, for example HTML (the browser DOM), canvas, or natively in Android or iOS.


### `React.DOM.*`
- A collection of ready-made HTML elements.
- You can use a number of HTML elements as React components via the `React.DOM` object. 

#### Special DOM attributes

- `className`: Sets the CSS class name for React DOM element.
- `htmlFor`: 
- `style`: Takes a JavaScript object.


### Components

- You build your UI using components and you combine these components in any way you see fit. 
- In your applications you’ll end up creating your own custom components, but to get you off the ground, React provides wrappers around HTML DOM elements.
- You use the wrappers via the React.DOM object. In this first example, you can see the use of the h1 component. It corresponds to the `<h1>` HTML element and is available to you using a call to `React.DOM.h1()`.
- Finally, you see the good old `document.getElementById("app")` DOM access. You use this to tell React where the application should be located in the page. This is the bridge crossing over from the DOM manipulation as you know it to the React-land.
- Once you cross the bridge from DOM to React, you don’t have to worry about DOM manipulation anymore, because React does the translation from components to the underlying platform (browser DOM, canvas, native app). 
- You don’t have to worry about DOM but that doesn’t mean you cannot. React gives you “escape latches” if you want to go back to DOM-land for any reason you may need.

#### Stateless vs. Stateful components



#### Composable components


#### Dynamically generated components from data sets




### Lifecycle 

Functions that you can implement in your `React.Component` class:

- constructor:
- `componentWillMount()`: Before mounting to the DOM.
- `componentDidMount()`: After mounting and rendering the DOM.
- `componentWillReceiveProps(nextProps)`: When component is about to receive properties.
- `shouldComponentUpdate(nextProps, nextState)-> bool`: Allows to optimize component's re-rendering by determining when to update and when to not.
- `componentWillUpdate(nextProps, nextState)`: Occurs right before component will update.
- `componentDidUpdate(prevProps, prevState)`: Occurs right after component is updated.
- `render()`:
- `componentWillUnmount()`: Allows to unbind and detach any event listeners or do other clean up work before component is unmounted.


### Higher order components (or functions)

- Replaces mixins in ES6 classes.


### JSX

- JSX is an optional HTML-like syntax that allows us to create a virtual DOM tree without using the `React.createElement()` method.
- JSX allows us to write HTML-like syntax in our JavaScript code. 
- More importantly, we can now clearly see what our HTML layout will look like once it's rendered. 
- JSX is a convenience tool and it comes with a price in the form of an additional transformation step. 
- Transformation of the JSX syntax into valid JavaScript syntax must happen before our "invalid" JavaScript code is interpreted.
