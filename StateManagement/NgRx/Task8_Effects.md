### Effects

- Install _@ngrx/effects_ by executing `ng add @ngrx/effects`.
- Check if the installation was successful by having a look at _app.module.ts_.
    - You should see _EffectsModule.forRoot([])_

- Open _book/store/book-collection.actions.ts_
- Create the action `loadBookStart`, being used to send a GET-Request to the API.
- Create the action `loadBookComplete`, being used to react to the response of the API.

- Create the file _book/store/book-collection.effects.ts_
- Implement the effect `load` that uses _BookApiService_ to load all books.
- Return the action `loadBookComplete`, when the books have been loaded successfully.
- Register _BookCollectionEffects_ in _book.module.ts_ by adding `EffectsModule.forFeature([BookCollectionEffects])`.

- Open _book/store/book-collection.reducer.ts_.
- Update the reducer function handling the action `loadBookComplete`.
    - It should save the books coming from the API to the store.

- Open _book.component.ts_.
- Dispatch the action `loadBookStart` triggering the GET-Request loading all books.

- Visit your app again.
- Check if the books are loaded instantly when you visit the book list.

## Hints

```typescript
// actions
export const loadBooksStart = createAction('[Book] Load Books Started');
export const loadBooksComplete = createAction('[Book] Load Books Completed', props<{ books: Book[] }>());
```

```typescript
//book-collections.effects.ts
@Injectable()
export class BookCollectionEffects{
  constructor(
    private readonly actions$: Actions,
    private readonly bookApi: BookApiService
  ) {}


  load = createEffect(() => {
    return this.actions$.pipe(
      ofType(loadBooksStart),
      exhaustMap(() => this.bookApi.getAll()),
      map(books => loadBooksComplete({books}))
    )
  })
}
```



[Solution](https://github.com/workshops-de/angular-advanced-workshop/compare/solve--ngrx-type-feature-state...solve--ngrx-introduce-effects)



### Bonus Aufgaben Effects

- Implement the feature "Create Book" using the NgRx infrastructure and effects.
- Implement the feature "Update Book" using the NgRx infrastructure and effects.
- Implement the feature "Delete Book" using the NgRx infrastructure and effects.
