## The Power of Hooks

---

### Me

---

### Should I Use Hooks?

@ul
- Optional
- Backwards-compatible
- Added in 16.8
- No plans to remove classes
@ulend

---

### Why Was it Added?

Hooks were added to allow a more powerful and expressive way to write state and other features between components without writing a class.

---
### Why Was it Added?

@ul
- Difficult to reuse stateful logic between components
- Hooks allow you to reuse without changing component hierarchy
- Hooks help you split components into smaller functions
- Classes are confusing
- Hooks let you use more of React's features without classes
- Make what you're already doing easer
@ulend

---

### When Should I Start Using Hooks?

"When you’re ready, we’d encourage you to start trying Hooks in new components you write... We don’t recommend rewriting your existing classes to Hooks unless you planned to rewrite them anyway (e.g. to fix bugs)." - [React team](https://reactjs.org/docs/hooks-faq.html#should-i-use-hooks-classes-or-a-mix-of-both)

---

### Hooks

- There are 10 hooks so far
- All start with "use"

---

### Hooks

@ul
- useState: functional component can have and update local state
- useEffect: perform side effects like logging, timers, mutations, or managing subscriptions
- useContext: takes context object and returns the current value for that context
@ulend

---

### Hooks

- useReducer
- useCallback
- useMemo
- useRef
- useImperativeHandle
- useLayoutEffect
- useDebug Value

---

@snap[northwest text-08 fragment]

```javascript
import React, { Component } from 'react';

class Counter extends Component {
    constructor() {
        super();
        this.state = {
            this.count = 0;
        }}
    handleClick = () => {
        this.setState = (prevState => ({count: prevState.count + 1})); }
    render() {
        const {count} = this.state;
        return (
            <div><button onClick={this.handleClick}>{count}</button></div>
        )
    }
}
```
@snapend

---

@snap[northwest span-50 text-08 fragment]
```javascript
import React, {useState} from ‘react’;
const [count, setCount] = useState(0);
const handleClick = () => this.setCount(count + 1);
const Counter = () => {
    return (
        <div><button onClick={this.handleClick}>{count}</button></div>
    );
}
```
@snapend

@snap[northeast span-50 text-08 fragment]
```javascript
import React, {useState} from ‘react’;
const [count, setCount] = useState(0);

const Counter = () => {
    return (
        <div><button onClick={() => setCount(count + 1)}>{count}</button></div>
    );
}
```
@snapend

---

```javascript
import React, {useState, useEffect} from ‘react’;
const [count, setCount] = useState(0);

// Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

const Counter = () => {
    return (
        <div><button onClick={() => setCount(count + 1)}>{count}</button></div>
    );
}
```