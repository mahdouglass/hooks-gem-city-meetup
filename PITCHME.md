## The Power of Hooks

---

@snap[north]
### Me
@snapend

@snap
Marissa Douglass
Web developer at Prudential
@mahdouglass
@snapend

---

@snap[north]
### Should I Use Hooks?
@snapend

@ul
- Optional
- Backwards-compatible
- Added in 16.8
- No plans to remove classes
@ulend

---

@snap[north]
### Why Was it Added?
@snapend

Hooks were added to allow a more powerful and expressive way to write state and other features between components without writing a class.

---

@snap[north]
### Why Was it Added?
@snapend

@ul
- Difficult to reuse stateful logic between components
- Hooks allow you to reuse without changing component hierarchy
- Hooks help you split components into smaller functions
- Classes are confusing
- Hooks let you use more of React's features without classes
- Make what you're already doing easer
@ulend

---

@snap[north]
### When Should I Start Using Hooks?
@snapend

"When you’re ready, we’d encourage you to start trying Hooks in new components you write... We don’t recommend rewriting your existing classes to Hooks unless you planned to rewrite them anyway (e.g. to fix bugs)." - [React team](https://reactjs.org/docs/hooks-faq.html#should-i-use-hooks-classes-or-a-mix-of-both)

---

@snap[north]
### Hooks
@snapend

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

@snap[north]
### Class example - useState
@snapend

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
        this.setState = (prevState => ({count: prevState.count + 1}));
    }
    render() {
        const {count} = this.state;
        return (
            <div>
                <button onClick={this.handleClick}>
                    {count}
                </button>
            </div>
        )
    }
}
```
@snapend

---
@snap[north]
### useState
@snapend

@snap[northwest span-100 text-08]
```javascript
import React, {useState} from ‘react’;
const [count, setCount] = useState(0);
const handleClick = () => this.setCount(count + 1);
const Counter = () => {
    return (
        <div>
            <button onClick={this.handleClick}>
                {count}
            </button>
        </div>
    );
}
```
@snapend

@snap[southwest span-55 text-08]
```javascript
import React, {useState} from ‘react’;
const [count, setCount] = useState(0);

const Counter = () => {
    return (
        <div>
            <button onClick={() => setCount(count + 1)}>
                {count}
            </button>
        </div>
    );
}
```
@snapend

---
@snap[north]
### Class example - useEffect
@snapend

@snap[span-100 text-10]
```javascript
class Counter extends Component {
    constructor(props) {
        super(props);
        this.state = {
            count: 0
        };
    }

    // Updates after component is rendered
    componentDidMount() {
        document.title = `You clicked ${this.state.count} times`;
    }

    // Updates after each state change
    componentDidUpdate() {
        document.title = `You clicked ${this.state.count} times`;
    }

    render() {
        return (
            <div>
                <p>You clicked {this.state.count} times</p>
                <button onClick={() => this.setState({ count: this.state.count + 1 })}>
                    Click me
                </button>
            </div>
        );
    }
}
```
@snapend

---

 ### useEffect

@snap[north span-100 text-10]
 ```javascript
 import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
@snapend