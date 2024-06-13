### Reducer

__Introduce Reducer__

- Create a new file `book/store/book-collection.slice.ts`.
- Create and export the interface `BookCollectionSlice` specifying the shape of your state slice.
- Create a new file `book/store/book-collection.reducer.ts`.
- Create a reducer function using _createReducer_.
- Specify an initial state.
- Handle the action `createBookStart`.
- Add the book provided by the action to a list.
- Keep in mind that list operations have to be immutable.
- Register the reducer in `book.module.ts` by adding `StoreModule.forFeature`.
- Specify a name for the feature containing the book state.
- Export the name in its own file `book/store/book.feature.ts` because we need to reuse the feature name later on.

__Manual Test__
- Return to your application.
- Create a new book in the form
- Submit the form
- Check the Redux DevTools
- Expect to see the dispatched action `createBookStart` to have changed the state by adding a book to the state.
## Hints

```ts
// book.feature.ts
export const bookFeatureName = 'book';

// book-collection.slice.ts
export interface BookCollectionSlice {
    entities: ReadonlyArray<Book>;
}

// book-collection.reducer.ts
import { createReducer } from '@ngrx/store';

export  const bookCollectionReducer = createReducer(/* ... */)

// book.module.ts
StoreModule.forFeature(bookFeatureName, { bookCollection: bookCollectionReducer })
```

[Solution](https://github.com/workshops-de/angular-advanced-workshop/compare/solve--ngrx-dispatch-action...solve--ngrx-use-reducer)
