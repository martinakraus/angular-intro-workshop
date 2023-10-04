### Selector

- Open the file _book/store/book.feature.ts_
- Create a feature selector using the constant specifying the feature name.
- Create the file _'book/store/book-collection.selectors.ts'_.
- Import the feature selector from _book.feature.ts_
- Create a selector providing the books of the store slice.
- Open the file _book/book-list.component.ts_
- Use the selector you have created instead of the inline projection function

- Create a new book.
- After navigating back to the book list you should see the created book selected from the store.

## Hints

```ts
import { createFeatureSelector, createSelector } from '@ngrx/store';

createFeatureSelector<{ bookCollection: BookCollectionSlice }>(bookFeatureName);

createSelector();
```
