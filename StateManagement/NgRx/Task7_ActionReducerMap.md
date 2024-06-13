### ActionReducerMap<T>

- Open _book/store/book.feature.ts_.
- Add the intrerface `BookState` representing the shape of the book-feature.
- Assign `ActionReducerMap<BookState>` to an exported const named `bookReducers`, collecting all reducers of the book-feature.

- Update the feature-selector to use the interface `BookState` instead of the inline typing.

- Open _book.module.ts_.
- Update the `StoreModule.forFeature`-declaration to use `bookReducer`, replacing the inline configuration for reducers.

## Hints

```typescript
// book.feature.ts
export const bookFeatureName = 'book';
...
export interface BookState {
  bookCollection: BookCollectionSlice;
}

export const bookReducers: ActionReducerMap<BookState> = {
  bookCollection: bookCollectionReducer
};

export const bookFeature = createFeatureSelector<BookState>(bookFeatureName);
```

[Solution](https://github.com/workshops-de/angular-advanced-workshop/compare/solve--ngrx-use-selectors-with-params...solve--ngrx-type-feature-state)
