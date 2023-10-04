### Router Store

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

