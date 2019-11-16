# The Power of Hooks

---

## Me

---

## Should I Use Hooks?

@ul
- Optional
- Backwards-compatible
- Added in 16.8
- No plans to remove classes
@ulend

---

## Why Was it Added?

Hooks were added to allow a more powerful and expressive way to write state and other features between components without writing a class.

@ul
- Difficult to reuse stateful logic between components
-- Hooks allow you to reuse without changing component hierarchy
- Complex components become more...complex
-- Hooks help you split components into smaller functions
- Classes are confusing
-- Need to know how "this" works
-- Have to remember to bind event handlers
-- Code is verbose
- Hooks let you use more of React's features without classes
- Make what you're already doing easer
@ulend

---

## When Should I Start Using Hooks?

"When you’re ready, we’d encourage you to start trying Hooks in new components you write. Make sure everyone on your team is on board with using them and familiar with this documentation. We don’t recommend rewriting your existing classes to Hooks unless you planned to rewrite them anyway (e.g. to fix bugs)." - React team https://reactjs.org/docs/hooks-faq.html#should-i-use-hooks-classes-or-a-mix-of-both

---

## Hooks

@ul
- There are 10 hooks so far
- All start with "use"
- useState(): functional component can have and update local state
- useEffect(): 
@ulend
