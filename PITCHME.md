## The Power of Hooks

---

@snap[north]
### Me
@snapend

@snap[west span-50]
#### Marissa Douglass
Web developer at Prudential
@mahdouglass
@snapend

@snap[east span-50]
![Marissa Douglass](assets/img/profile-pic.jpg)
@snapend

---

@snap[north span-100]
### Why Was it Added?
@snapend

Hooks were added to allow a more powerful and expressive way to write state and other features between components without writing a class.

---

@snap[north span-100]
### Why Was it Added?
@snapend

@snap
@ul
- Difficult to reuse stateful logic between components
- Classes are confusing
- Hooks let you use more of React's features without classes
- Don't have to change component hierarchy
- Can split components into smaller functions
- Make what you're already doing easier
@ulend
@snapend

---

@snap[north span-100]
### Should I Use Hooks?
@snapend

@ul
- Added in 16.8
- No plans to remove classes
- Optional
- Backwards-compatible
@ulend

---

@snap[north span-100]
### When Should I Start Using Hooks?
@snapend

@snap
"When you’re ready, we’d encourage you to start trying Hooks in new components you write... We don’t recommend rewriting your existing classes to Hooks unless you planned to rewrite them anyway (e.g. to fix bugs)." - [React team](https://reactjs.org/docs/hooks-faq.html#should-i-use-hooks-classes-or-a-mix-of-both)
@snapend

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

@snap[north]
### Hooks
@snapend

@ul
- useReducer
- useCallback
- useMemo
- useRef
- useImperativeHandle
- useLayoutEffect
- useDebugValue
@ulend

---

### Tips

@ul
- Don't call hooks inside loops, conditions, or nested functions
- Call hooks in React functions not regular JavaScript functions
- Recommended plugin:
```git
npm install eslint-plugin-react-hooks --save-dev
```
@ulend

---

@snap[north span-100]
### Class example - useState
@snapend

@snap[northwest text-08 fragment]

```javascript
class ClassCounter extends Component {
 constructor() {
   super();
   this.state = {
     count: 0
   };
 }
 render() {
   return (
     <div>
       <button onClick={() => this.setState({ count: this.state.count + 1 })}>{this.state.count}</button>
     </div>
   );
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

---

@snap[north]
### Custom Hooks
@snapend

@ul
- Just a regular function
- Same naming convention, start with use
- May call other hooks
- Custom arguments
- Optional return
- All state and effects are isolated
@ulend
