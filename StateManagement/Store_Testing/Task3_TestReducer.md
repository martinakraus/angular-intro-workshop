### Test | Reducer

- Create the file _book/store/book-collection.reducer.spec.ts_
- Write a test ensuring that action `bookCreateComplete` adds a book to the store.


## Hints

```ts
```ts
const initialState: EntityState<Book> = { entities: {}, ids: [] };
const action = createBookComplete({ book });
const state = bookCollectionReducer(initialState, action);
```
