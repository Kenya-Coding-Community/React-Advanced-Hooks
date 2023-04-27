# React-Advanced-Hooks

---

## Team

- Ruperth Nyagesoa
- Milhan Osman
- Abdirashid Noor
- Sharleen Ringa

---
It's important to understand that hooks are basically just functions.
Hooks : The Hooks consists of two fundamental and primary hooks which are mentioned below.
In addition to these fundamental hooks, there are a number of auxiliary hooks which can be used for advanced behaviour.
Let's see one by one : 
- useState.
- useEffect. 
- useContext.
- useRef.

##### note:
React Hooks are functions that let us hook into the React state and lifecycle features from function components. By this, we mean that hooks allow us to easily manipulate the state of our functional component without needing to convert them into class components.

### Topic: Discussing Hooks
#### useState

First, we need to import the useState hook:

```jsx
import React, { useState } from 'react'; 
```
useState returns a pair, the current state value and a function, that lets you change the state.

useState takes one argument, which is the initial value of the state.

example.

```jsx
function Hello() {
  const [name, setName] = useState("David");

  return <h1>Hello {name}.</h1>;
}
```
In the example above, we create a name state variable and a setName function. The square brackets syntax is called array destructuring. It assigns the name variable to the current state value, and setName to the function that allows to change the state. You can name these variables anything you like.
Then, we pass "David" as the initial value for our name variable to useState().

#### useEffect
useEffect is a React Hook that lets you synchronize a component with an external system.


```jsx
useEffect(setup, dependencies?)
```
useEffect is a Hook, so you can only call it at the top level of your component or your own Hooks. You can’t call it inside loops or conditions. If you need that, extract a new component and move the state into it.

Call useEffect at the top level of your component to declare an Effect:

```jsx
import { useEffect } from 'react';
import { createConnection } from './chat.js';

function ChatRoom({ roomId }) {
  const [serverUrl, setServerUrl] = useState('https://localhost:1234');

  useEffect(() => {
    const connection = createConnection(serverUrl, roomId);
    connection.connect();
    return () => {
      connection.disconnect();
    };
  }, [serverUrl, roomId]);
  // ...
}
```
useEffect returns undefined.

This means useEffect by itself doesn't return a value. Instead, it can have side effects, such as updating state, subscribing or unsubscribing from external resources, or modifying the DOM. When React renders a component that has an effect hook like useEffect, it will run the effect after rendering the component.

If you want to return a cleanup function from your effect, you can define a function that does the necessary cleanup tasks, and then return it at the end of your effect. For example:

```jsx
useEffect(() => {
  // do some effect
  const cleanupFunction = () => {
    // do some cleanup
  }
  return cleanupFunction;
}, [/* dependency array */]);
```
In this example, the effect itself doesn't return a value - instead, it defines a cleanup function that is returned when the component is unmounted or when the effect is re-run with different dependencies. The cleanup function is responsible for doing any necessary cleanup tasks, such as unsubscribing from an external resource, cleaning up event listeners, or resetting state.

#### useRef
useRef is a React Hook that lets you reference a value that’s not needed for rendering.

```jsx
const ref = useRef(initialValue)
```
Call useRef at the top level of your component to declare a ref.

```jsx
import { useRef } from 'react';

function MyComponent() {
  const intervalRef = useRef(0);
  const inputRef = useRef(null);
  // ...
```
useRef returns an object with a single property:

Initially, it’s set to the initialValue you have passed. You can later set it to something else. If you pass the ref object to React as a ref attribute to a JSX node, React will set its current property.
On the next renders, useRef will return the same object.

You can mutate the ref.current property. Unlike state, it is mutable. However, if it holds an object that is used for rendering (for example, a piece of your state), then you shouldn’t mutate that object.
#### useContext
useContext is a React Hook that lets you read and subscribe to context from your component.

```jsx
const value = useContext(SomeContext)
``` 

Call useContext at the top level of your component to read and subscribe to context.

```jsx
import { useContext } from 'react';

function MyComponent() {
  const theme = useContext(ThemeContext);
  // ...
```
useContext returns the context value for the calling component. It is determined as the value passed to the closest SomeContext.Provider above the calling component in the tree. If there is no such provider, then the returned value will be the defaultValue you have passed to createContext for that context. The returned value is always up-to-date. React automatically re-renders components that read some context if it changes.

useContext() call in a component is not affected by providers returned from the same component. The corresponding <Context.Provider> needs to be above the component doing the useContext() call.

#### useReducer

useReducer is a React Hook that lets you add a reducer to your component.

```jsx
const [state, dispatch] = useReducer(reducer, initialArg, init?)
```
 
Call useReducer at the top level of your component to manage its state with a reducer.

```jsx
import { useReducer } from 'react';

function reducer(state, action) {
  // ...
}

function MyComponent() {
  const [state, dispatch] = useReducer(reducer, { age: 42 });
  // ...
```
useReducer returns an array with exactly two values:

The current state. During the first render, it’s set to init(initialArg) or initialArg (if there’s no init).

The dispatch function that lets you update the state to a different value and trigger a re-render.

##### note:
useReducer is a Hook, so you can only call it at the top level of your component or your own Hooks.You can’t call it inside loops or conditions.If you need that, extract a new component and move the state into it.

Let's see the others : 
- useCallback.
- useMemo. 
- useImperativeHandle. 
- useLayoutEffect. 
- useDebugValue.

[find link attached](https://react.dev/reference/react)

##### note:
React Hooks are functions that let us hook into the React state and lifecycle features from function components. By this, we mean that hooks allow us to easily manipulate the state of our functional component without needing to convert them into class components.
