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

## Hints

```ts
// book-new.component.ts
import { Store } from '@ngrx/store';

this.store.dispatch(createBookStart());
```
