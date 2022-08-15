# Reading Day 29

## [Home Page](/README.md)

## useReducer

```js
const [state, dispatch] = useReducer(reducer, initialArg, init);
```

useReducer is usually preferable to useState when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one.

```js
const initialState = {count: 0};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```

If you return the same value from a Reducer Hook as the current state, React will bail out without rendering the children or firing effects.

`useReducer` returns an array that holds the current state value and a `dispatch` function to which you can pass an action and later invoke it.

* A store: An immutable object that holds the application’s state data.

* A reducer: A function that returns some state data, triggered by an action type.

* An action: An object that tells the reducer how to change the state. It must contain a type property and can contain an optional payload property.

## useState vs. useReducer

useState is a basic Hook for managing simple state transformation, and useReducer is an additional Hook for managing more complex state logic. However, it’s worth noting that useState uses useReducer internally, implying that you could use useReducer for everything you can do with useState.

However, there are some major differences between these two Hooks. With useReducer, you can avoid passing down callbacks through different levels of your component. Instead, useReducer allows you to pass a provided dispatch function, which in turn will improve performance for components that trigger deep updates.

However, this does not imply that the useState updater function is newly called on each render. When you have a complex logic to update state, you simply won’t use the setter directly to update state. Instead, you’ll write a complex function, which in turn would call the setter with updated state.

Therefore, it’s recommended to use useReducer, which returns a dispatch method that doesn’t change between re-renders, and you can have the manipulation logic in the reducers.

It’s also worth noting that with useState, the state updater function is invoked to update state, but with useReducer, the dispatch function is invoked instead, and an action with at least a type is passed to it.

Now, let’s take a look at how both Hooks are declared and used.
