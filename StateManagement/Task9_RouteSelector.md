## Router Store

- Install the RouterStore by executing `ng add @ngrx/router-store`
- Register the RouterStore's reducer in _app.module.ts_: `StoreModule.forRoot({ router: routerReducer }, { /* ... */ })`
- Create the file _app/store/router/router.selectors.ts_
- Reexport all RouterStore's selctors (see: [NgRx Docs | Selectors](https://ngrx.io/guide/router-store/selectors)). Note: This link will forward you to the most recent version of NgRx where some API's might have changed. To be on the safe side, select on the left side the version which matches the installed `@ngrx/router-store`-version in your project.

- Open _book/store/book-collection.selectors.ts_
- Update `bookByIsbn` to use the RouterStore's selector `selectRouteParam('isbn')`
    - Therefore you need to compose two selectors: _bookCollection & selectRouteParam_
    - This means `bookByIsbn` no longer takes a parameter because we now get the route parameter from the Store.
- Update all usages of `bookByIsbn`
- Remove the `ActivatedRoute`-Service from the respective components.

> _Notice that each component that is fully migrated has only one dependency, the Store._

## Hints

```typescript
app/store/router/router.selectors.ts

import { getRouterSelectors } from '@ngrx/router-store';

// `router` is used as the default feature name. You can use the feature name
// of your choice by creating a feature selector and pass it to the `getRouterSelectors` function
// export const selectRouter = createFeatureSelector<RouterReducerState>('yourFeatureName');

export const {
  selectCurrentRoute, // select the current route
  selectFragment, // select the current route fragment
  selectQueryParams, // select the current route query params
  selectQueryParam, // factory function to select a query param
  selectRouteParams, // select the current route params
  selectRouteParam, // factory function to select a route param
  selectRouteData, // select the current route data
  selectRouteDataParam, // factory function to select a route data param
  selectUrl, // select the current url
  selectTitle // select the title if available
} = getRouterSelectors();
```
```typescript
export const selectBookByIsbn = createSelector(
  selectRouteParam('isbn'),
  selectBookCollection,
  (isbn, books) => books.find(book => book.isbn === isbn)
)
```


```typescript
//book-detail.component.ts
    this.book$ = this.store.select(selectBookByIsbn).pipe(
      filter((book): book is Book => !!book)
    )
```

[Solution](https://github.com/workshops-de/angular-advanced-workshop/commit/bef798befea50bb0db54b6cb1336a644dcce93e0)
