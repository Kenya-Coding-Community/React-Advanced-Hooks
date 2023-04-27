# React-Advanced-Hooks

---

## Team

- Ruperth Nyagesoa
- Milhan Osman
- Abdirashid Noor
- Sharleen Ringa

---
It's important to understand that hooks are basically just functions.
💎Hooks : ✨ The Hooks consists of two fundamental and primary hooks which are mentioned below.
In addition to these fundamental hooks, there are a number of auxiliary hooks which can be used for advanced behaviour.
Let's see one by one : 
- useState.
- useEffect. 
- useReducer. 
- useCallback.
- useMemo. 
- useRef. 
- useImperativeHandle. 
- useLayoutEffect. 
- useDebugValue.
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
#### useContext
useContext is a React Hook that lets you read and subscribe to context from your component.

```jsx
const value = useContext(SomeContext)
```
useContext(SomeContext) 
Call useContext at the top level of your component to read and subscribe to context.

```jsx
import { useContext } from 'react';

function MyComponent() {
  const theme = useContext(ThemeContext);
  // ...
```


