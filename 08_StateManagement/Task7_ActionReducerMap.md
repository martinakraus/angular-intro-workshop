### ActionReducerMap<T>

- Open _book/store/book.feature.ts_.
- Add the intrerface `BookState` representing the shape of the book-feature.
- Assign `ActionReducerMap<BookState>` to an exported const named `bookReducers`, collecting all reducers of the book-feature.

- Update the feature-selector to use the interface `BookState` instead of the inline typing.

- Open _book.module.ts_.
- Update the `StoreModule.forFeature`-declaration to use `bookReducer`, replacing the inline configuration for reducers.

