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

