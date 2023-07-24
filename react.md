<h1 align="center">REACT</h1>

### PURE FUNCTION

A pure function is a function with the following characteristics:

- Minds its own business: It does not change any variables that existed outside of the function
- Same inputs, same output

### PURE COMPONENT

PureComponent is similar to Component but it skips re-renders for same props and state

### GENERATE ID OR KEY

https://www.npmjs.com/package/uuid

### RENDER AND COMMIT

1. Triggering: Trigger an render

- Initial render
- State has been updated

2. Rendering: React renders your components

- On initial render: React will call the root component
- For subsequent renders, React will call the function component whose state update triggered the render:
  - React calls your function
  - Your function returns a new JSX snapshot.

3. Committing: React commit changes to the DOM

- For the initial render, React will use the appendChild() DOM API to put all the DOM nodes it has created on screen.
- For re-renders, React will apply the minimal necessary operations (calculated while rendering!) to make the DOM match the latest rendering output.

### STATE

store objects in state => `mutating state`

numbers, booleans, and strings. They were `immutable`

```c
const [position, setPosition] = useState({ x: 0, y: 0 });
position.x = 5;
```

`Mutation` : it is possible to change the contents of the object itself.

```c
const nextPosition = {};
nextPosition.x = e.clientX;
nextPosition.y = e.clientY;
setPosition(nextPosition);
```

`Local mutation` : Mutating an object you’ve just created

Components as `controlled` (driven by props) or `uncontrolled` (driven by state).

`Lifting state up` - `Move state down`

React `preserves` a component’s state for as long as it’s being rendered at its position in the UI tree. If it gets removed, or a different component gets rendered at the same position, React discards its state.

Resetting state at the same position :

- Rendering a component in different positions
- Resetting state with a key

### QUEUEING A SERIES OF STATE UPDATES

```c
<button onClick={() => {
  setNumber(number + 1);
  setNumber(number + 1);
  setNumber(number + 1);
  }}>+3</button>
```

`Batching` : React waits until all code in the event handlers has run before processing your state updates. This also means that the UI won’t be updated until after your event handler

```c
<button onClick={() => {
  setNumber(n => n + 1);
  setNumber(n => n + 1);
  setNumber(n => n + 1);
  }}>+3</button>
```

Here, n => n + 1 is called an `updater function`

### useRef

```c
// Inside of React
function useRef(initialValue) {
  const [ref, unused] = useState({ current: initialValue });
  return ref;
}
```

- Mutable
- Doesn’t trigger re-render when you change it
- You shouldn’t read (or write) the current value during rendering. You can read or write refs in event handlers

```c
flushSync(() => {
  setTodos([ ...todos, newTodo]);
});
listRef.current.lastChild.scrollIntoView();
```

Flushing state updates synchronously with flushSync

### useEffect

Thinking from the component perspective:

- A component `mounts` when it’s added to the screen.
- A component `updates` when it receives new props or state, usually in response to an interaction.
- A component `unmounts` when it’s removed from the screen.

Thinking from the Effect’s perspective:

- `start synchronizing`
- `stop synchronizing`

React compares the dependency values using the `Object.is` comparison

`Race condition` : two different requests “raced” against each other and came in a different order than you expected.

https://maxrozen.com/race-conditions-fetching-data-react-with-useeffect

### STRICT MODE

- React remounts every component once after mount (state and DOM are preserved). This helps you find Effects that need cleanup and exposes bugs like race conditions early
- Fixing bugs found by double rendering in development
- Fixing bugs found by re-running Effects in development
- Fixing deprecation warnings enabled by Strict Mode

### useMemo

```c
console.time('filter array');
const visibleTodos = getFilteredTodos(todos, filter);
console.timeEnd('filter array');

console.time('filter array');
const visibleTodos = useMemo(() => {
  return getFilteredTodos(todos, filter); // Skipped if todos and filter haven't changed
}, [todos, filter]);
console.timeEnd('filter array');
```

### RESET ALL STATE WITH A KEY

https://react.dev/learn/you-might-not-need-an-effect#resetting-all-state-when-a-prop-changes

### CALCULATE EVERYTHING DURING RENDERING

https://react.dev/learn/you-might-not-need-an-effect#updating-state-based-on-props-or-state
