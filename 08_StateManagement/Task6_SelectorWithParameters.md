### Selectors with Parameters 

- Open _book/store/book-collection.selectors.ts_.
- Add the selector `bookByIsbn` that accepts an _ISBN_ as parameter.
- Make the selector returning one book that has the given _ISBN_.

- Open _book-details.component.ts_.
- Update initialization of `book$` by selecting the book from the store instead of using `BookApiService`.
- Use the selector `bookByIsbn`

## Hints

```ts
// book-collection.selectors.ts
export const bookByIsbn = (isbn: string) =>
  createSelector(<reuse the selector you have written to select the books>, books => books.find(book => book.isbn === isbn));

// fragment from book-details.component.ts
switchMap(params => this.store.select(bookByIsbn(params.isbn)))
```
