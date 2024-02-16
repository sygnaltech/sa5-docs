---
description: Underlying state handlers which MAY BE made available for system versatility
---

# State Handlers





#### Comparison and Use Cases

* **Redux** is well-suited for large-scale applications where managing global state in a predictable manner is critical. Its strict architecture and single state tree make it easier for team collaboration and maintainability.
* **MobX** can be a good choice for smaller to medium-sized projects where quick development and minimal boilerplate are prioritized. It's also beneficial when you have complex data that's frequently updated from many parts of the app.

Both libraries have vibrant ecosystems and are widely used in the community. The choice between them often comes down to the specific needs of the project and the team's familiarity with functional programming (Redux) versus reactive programming (MobX).

## Technical Notes

Both Redux and MobX are available to be integrated into your TypeScript project. Both have good support for TypeScript, offering type definitions that you can use to ensure type safety and take advantage of TypeScript's features like interfaces and generics for state actions, reducers, and stores.

Redux has official type definitions, which you can install from npm:

```
npm install @types/react-redux
```

You can use Redux with TypeScript by defining types for your state and actions. Redux Toolkit (`@reduxjs/toolkit`), which is the recommended approach to use Redux today, is also fully typed and provides utilities to simplify the usage with TypeScript.

Here’s an example of how you might define your Redux state and actions with TypeScript:

```
import { createAction, createReducer } from '@reduxjs/toolkit';

interface MyState {
  value: number;
}

const initialState: MyState = { value: 0 };

const increment = createAction('increment');

const myReducer = createReducer(initialState, (builder) => {
  builder.addCase(increment, (state, action) => {
    state.value += 1;
  });
});

```



#### MobX with TypeScript

MobX also provides excellent TypeScript support. You can define your state and actions with TypeScript classes and decorators, though decorators are an experimental feature and may require enabling in your `tsconfig.json`.

You can install MobX with npm:

```
npm install mobx mobx-react

```

```
import { makeAutoObservable } from "mobx";

class MyState {
  value = 0;

  constructor() {
    makeAutoObservable(this);
  }

  increment() {
    this.value += 1;
  }
}

const myState = new MyState();

```



### Storage

\
Redux and MobX by themselves do not automatically handle persisting state to web storage (localStorage or sessionStorage) or cookies. However, they can be easily integrated with libraries that enable this functionality.

For Redux, the most common library used for persistence is `redux-persist`. It allows you to save your Redux store (or parts of it) to storage and rehydrate the state on app initialization.

Here's a basic example of how to use `redux-persist`:

```
import { createStore } from 'redux';
import { persistStore, persistReducer } from 'redux-persist';
import storage from 'redux-persist/lib/storage'; // defaults to localStorage for web

const persistConfig = {
  key: 'root',
  storage,
};

const persistedReducer = persistReducer(persistConfig, rootReducer);

const store = createStore(persistedReducer);
const persistor = persistStore(store);

export { store, persistor };

```

In this code, `rootReducer` is your main Redux reducer. The `persistStore` function wraps your store and handles the process of saving and rehydrating the state. The `storage` object from `redux-persist` defaults to using `localStorage`, but you can configure it to use `sessionStorage` or other custom storage engines.

For MobX, automatic persistence is not built-in, but you can use libraries like `mobx-persist` or manually write to localStorage or sessionStorage within your actions. With MobX, it’s more of a manual process where you decide exactly when and what to persist and rehydrate.

Here's a simple example of how you might manually persist part of your MobX store:

```
import { observable, action, toJS } from 'mobx';

class Store {
  @observable myState = {};

  @action saveState() {
    localStorage.setItem('myState', JSON.stringify(toJS(this.myState)));
  }

  @action loadState() {
    const savedState = localStorage.getItem('myState');
    if (savedState) {
      this.myState = JSON.parse(savedState);
    }
  }
}

const myStore = new Store();
myStore.loadState(); // Call this when initializing your app

export default myStore;

```

In the example above, `saveState` is an action that serializes part of the store state to a JSON string and saves it in `localStorage`. The `loadState` action retrieves the state from `localStorage` and parses it back into an object.

Both `redux-persist` and `mobx-persist` (or manual approaches) offer flexibility in how you handle data serialization and rehydration. They also provide hooks and configuration options to refine when and how state is persisted, such as throttling save operations or integrating with encryption libraries if needed.

Remember, when storing sensitive information, consider security implications. Local storage and cookies are susceptible to XSS attacks, so sensitive data should be stored securely and never in plain text.







