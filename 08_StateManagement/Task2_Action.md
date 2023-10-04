### Dispatch an Action

- Create a new directory _book/store/_.
- Create the file _store/book-collection.actions.ts_.
- Create the action `createBookStart` that requires the property _{ book: Book}_.
- Make sure that the action is exported.
- Open _book-new.component.ts_
- Inject the _Store_
- Dispatch `createBookStart` in the method `create`
- Open Redux DevTools in your browser.
- Make sure that the dispatched action appears in the action log.
- Take some time to have a look what features the DevTools have.

* This task also has a bonus part.

## Hints

```ts
// book-new.component.ts
import { Store } from '@ngrx/store';

this.store.dispatch(createBookStart());
```

[Solution](https://github.com/workshops-de/angular-advanced-workshop/compare/solve--ngrx-store-setup...solve--ngrx-dispatch-action)


## Bonus

__Replace relative import paths with path-alias__

- Create a barrel file (index.ts) inside _store/book_
- Make the barrel file export _book-collection.actions.ts_
- Open the root-_tsconfig.json_
- Add the path alias __@store/book__ that points to _./src/app/book/store/index_
- Update the import-path of createBookStart to use __@store/book__ instead of the relative path.

```json
"paths": {
  "@store/book": ["./src/app/book/store/index"]
}
```

```ts
import { createBookStart } from '@store/book';
```
