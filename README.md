> Howdy 👋
>
> We have a release candidate (RC) for v3. 🎉
>
> v3 is aimed at being our long term support (LTS) release, with the intention to avoid breaking changes and minimise the features that we add to the library.
>
> [The website for the RC can be found here](https://easy-peasy-v3.now.sh)
>
> For those currently using v2; you can find the notes on the breaking changes included within the [v3 PR](https://github.com/ctrlplusb/easy-peasy/pull/216).

---

<p>&nbsp;</p>
<p align='center'>
  <img src="https://i.imgur.com/UnPLVly.png" width="280" />
</p>
<p align='center'>Easy peasy state for React</p>
<p>&nbsp;</p>

[![npm](https://img.shields.io/npm/v/easy-peasy.svg?style=flat-square)](http://npm.im/easy-peasy)
[![MIT License](https://img.shields.io/npm/l/easy-peasy.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![Travis](https://img.shields.io/travis/ctrlplusb/easy-peasy.svg?style=flat-square)](https://travis-ci.org/ctrlplusb/easy-peasy)
[![Codecov](https://img.shields.io/codecov/c/github/ctrlplusb/easy-peasy.svg?style=flat-square)](https://codecov.io/github/ctrlplusb/easy-peasy)

**Step 1 - Create your store**

```javascript
const store = createStore({
  todos: {
    items: ['Create store', 'Wrap application', 'Use store'],
    add: action((state, payload) => {
      state.items.push(payload)
    })
  }
});
```

**Step 2 - Wrap your application**

```javascript
function App() {
  return (
    <StoreProvider store={store}>
      <TodoList />
    </StoreProvider>
  );
}
```

**Step 3 - Use the store**

```javascript
function TodoList() {
  const todos = useStoreState(state => state.todos.items)
  const add = useStoreActions(actions => actions.todos.add)
  return (
    <div>
      {todos.map((todo, idx) => <div key={idx}>{todo}</div>)}
      <AddTodo onAdd={add} />
    </div>
  )
}
```

## Highlights

  - Zero configuration
  - No boilerplate
  - Intuitive API
  - React hooks to use store within components
  - Thunks for data fetching and side effects
  - Computed properties - i.e. derived data
  - Global, shared, or component level stores
  - Immutable data store under the hood
  - Includes robust TypeScript definitions
  - React Native supported
  - Includes APIs to aid testing
  - Wraps Redux, all the radness, without the boilerplate
  - Redux Dev Tools support preconfigured
  - Supports customisation of the underlying Redux store

## Introduction

Easy Peasy provides you with an intuitive API to quickly and easily manage the state for your React application. Batteries are included - no configuration is required to support derived state, API calls, performance optimisation, developer tools etc.

## Documentation

The [official website](https://easy-peasy.now.sh) contains all the tutorials and documentation you will need to get started.