### Test | Action - Effect - Reducer - Selector

- Create _book/store/book-collection.effects.spec.ts_
- Write a test verifying that dispatching `createBookStart` ends up in caching the created book in the Store.
- The flow of the test could be
    - Set up a mock for the BookApiService
    - Configure the TestBed to import EffectsModule.forRoot, StoreModule.forRoot, StoreModule.forFeature.
    - Dispatch the action createBookStart with a mocked book
    - Use the selector bookCollection to query the books of the store
    - Assert that the dispatched book is part of the collection


## Hints

```ts
// Service Mock
bookApiMock = jasmine.createSpyObj<BookApiService>(['create']);
bookApiMock.create.and.returnValue(of(book));

// TestBed
TestBed.configureTestingModule({
  imports: [
    RouterTestingModule,
    EffectsModule.forRoot([BookCollectionEffects]),
    StoreModule.forRoot({}),
    StoreModule.forFeature(bookFeatureName, bookReducers)
  ],
  providers: [{ provide: BookApiService, useFactory: () => bookApiMock }]
});

// Act
store.dispatch(createBookStart({ book }));

// Assertion
store.select(bookCollection).subscribe(books => {
  expect(books).toContain(book);
  done();
});
```
